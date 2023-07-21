<template>
  <h1
    style="margin: 0px; padding: 20px; background-color: #73685d; color: white; width: 100%;"
  >
    관리자 페이지
  </h1>
  <div style="display: flex; /*  background-color: bisque; color: brown */" >
    <div id="sidebar">
      <h2 style="font-size: 50px;">sidebar</h2>
      <a @click="$store.commit('printList', 0); $store.dispatch('getUserStateList');" style="cursor: pointer; padding: 10px; margin: 5px 0;"
        >사용자 목록</a
      >
      <br />
      <a @click="$store.commit('printList', 1); $store.dispatch('getUserStateList');" style="cursor: pointer; padding: 10px; margin: 5px 0;"
        >공인중개사 목록</a
      >
      <br />
      <a @click="$store.commit('printList', 2); $store.dispatch('getUserStateList');" style="cursor: pointer; padding: 10px; margin: 5px 0;"
        >매물 목록</a
      >
      <br />
      <a href="#">공지사항</a>
    </div>
    <div style="margin: 0 auto" v-if="!$store.state.login"></div>
    <div style="margin: 0 auto" v-if="$store.state.login">
      <Admin_main></Admin_main>
    </div>
  </div>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue-3/dist/bootstrap-vue-3.css'
import Admin_main from "./components/Admin_main.vue";
export default {
  name: "App",
  created() {
    this.$store.dispatch("getUserStateList");
  },
  components: {
    Admin_main,
  },
};
</script>

<style>
@import url("./assets/css/common.css");
a {
  text-decoration: none;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
