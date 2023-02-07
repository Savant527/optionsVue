<template>
  <button @click="show = !show">Menú</button>
  <transition name="fade">
    <Menu v-show="show" />
  </transition>
  <br/>
  <br/>
  <br/>
  <br/>
  <br/>
  <br/>
  <div>
    <Modal/>
  </div>
  <br/>
  <br/>
  <br/>
  <br/>
  <div>{{ text }}</div>
  <div>{{ algo }}</div>
</template>

<script>
// import { defineAsyncComponent } from "vue";
// const HelloWorld = defineAsyncComponent(() =>
//   import(`./components/HelloWorld.vue`)
// );
import Menu from "./components/Menu.vue";
import Modal from "./components/Modal.vue";
import base from "@/mixins/base";

export default {
  name: "App",
  components: {
    Menu,
    Modal
  },
  mixins: [base],
  data() {
    return {
      text: "Hola Vue",
      show: false,
    };
  },
  beforeCreate(){
    console.log("beforeCreate", this.$data, this.$el);
  }, created() {
    console.log("created", this.$data, this.$el);
  },
  mounted() {
    console.log("mounted", this.$data, this.$el);
  },
  // data() {
  //   return {
  //     componente: "HelloWorld",
  //   };
  // },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
.fade-leave-active,
.fade-enter-active {
  transition: opacity 0.5s ease;
}
</style>
