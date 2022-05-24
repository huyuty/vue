<template>
  <main>
    <section class="py-5 container">
      <table class="table">
        <thead>
        <tr>
          <th v-for="col in cols" :key="col.name" scope="col">{{ col.title }}</th>
        </tr>
        </thead>
        <tbody>
        <tr v-for="row in rows" :key="row.id">
          <td v-for="col in cols" :key="col.name">{{ row[col.name] }}</td>
        </tr>
        </tbody>
      </table>
      <form @submit="handleSubmit">
        <div class="row mb-3">
          <div class="col">
            <input type="text" class="form-control"  placeholder="Фамилия" id="surname" aria-label="First name">
          </div>
          <div class="col">
            <input type="text" class="form-control" placeholder="Имя" id="name" aria-label="Last name">
          </div>
          <div class="col">
            <input type="text" class="form-control" placeholder="Отчество" id="dad_name" aria-label="Last name">
          </div>
        </div>
          <div class="row mb-3">
            <div class="col">
              <input type="text" class="form-control" placeholder="Адрес электронной почты" id="mail" aria-label="Last name">
            </div>
            <div class="col">
              <input type="text" class="form-control" placeholder="Телефон" id="phone" aria-label="Last name">
            </div>
            <div class="col">
              <input type="text" class="form-control" placeholder="Дата рождения" id="born" aria-label="Last name">
            </div>

        </div>
        <button type="submit" class="btn btn-dark">Сохранить</button>
      </form>
      <div v-for="row in rows" class="col" :key="row.id">
        <div class="btn-group" id="for_action">
          <button type="button" class="btn btn-sm btn-danger" @click="removeCard(row.id)">Удалить</button>
        </div>
      </div>
    </section>
  </main>
</template>

<script>

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  computed: {
    cols() {
      return this.$store.state.cols
    },
    rows() {
      return this.$store.state.rows
    }
  },
  methods: {
    handleSubmit(e) {
      e.preventDefault()
      this.$store.commit('addRow', {surname: e.target.elements.surname.value,
                                    name: e.target.elements.name.value,
                                    dad_name: e.target.elements.dad_name.value,
                                    mail: e.target.elements.mail.value,
                                    phone: e.target.elements.phone.value,
                                    born: e.target.elements.born.value,
                                    for_action: e.target.elements.for_action,
                                    })
    },
    removeCard(id) {
      this.$store.dispatch('removeRow', id)
    }
  }
}

</script>

<style scoped>

</style>