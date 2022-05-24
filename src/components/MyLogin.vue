<template>
  <div class="container-xxl">
    <container>
    <body class="text-center">
    <form class="form-signin">
      <h1 class="h3 mb-3 font-weight-normal">Авторизация</h1>
      <div class="mb-3">
        <input type="email" id="inputEmail" class="form-control" placeholder="Электронный адрес" required="" autofocus="">
      </div>
      <input type="password" id="inputPassword" class="form-control" placeholder="Пароль" required="">
      <div class="checkbox mb-3">
        <label>
          <input type="checkbox" value="remember-me"> Запомнить меня
        </label>
      </div>
      <button class="btn btn-lg btn-danger" type="submit">Войти</button>
    </form>
    </body>
    </container>
  </div>

</template>

<script>
export default {
  name: "MyLogin"
}
</script>

<style scoped>
input {
  border-radius: 17.25rem;
  margin: auto;
  width: 50%;

}
</style>