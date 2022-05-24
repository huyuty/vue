<template>
  <MyHeader />
  <router-view ></router-view>
  <my-footer />
</template>

<script>
import MyHeader from "@/components/MyHeader.vue"
export default {
  name: 'App',
  components: {
    MyHeader
  }


}
</script>

<style>
</style>
