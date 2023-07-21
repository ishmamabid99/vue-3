<template>
  <nav class="navbar">
    <div class="logo">
      <img :src="logo" />
    </div>
    <div class="options">
      <div v-for="(item, index) in options" :key="index">
        <p v-if="index === 0" @click="toggleModalClick" class="nav-items">
          {{ item }}
        </p>
        <p v-else class="nav-items">
          {{ item }}
        </p>
      </div>
    </div>
  </nav>
  <div v-if="showModal">
    <FormModal :svgImage="leftImage" @close="toggleModalClick">
      <template v-slot:title>
        <h1 class="login-title">Login</h1>
      </template>
      <LoginForm />
    </FormModal>
  </div>
</template>

<script>
import FormModal from "./FormModal";
import LoginForm from "./LoginForm";
import logo from "../assets/logo.png";
import image from "../assets/login-bank.svg";
console.log(image);
export default {
  props: ["options"],
  data() {
    return {
      logo: logo,
      leftImage: image,
      showModal: false,
    };
  },
  methods: {
    toggleModalClick() {
      this.showModal = !this.showModal;
    },
  },
  components: { FormModal, LoginForm },
};
</script>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
  background: white;
}
.options {
  margin-right: 30px;
  display: flex;
  flex-direction: row-reverse;
}
.nav-items {
  margin-right: 50px;
  color: #4682c0;
  cursor: pointer;
  font-size: 1.35rem;
}
.logo {
  margin-left: 30px;
}
.logo img {
  width: 10rem;
}
.login-title {
  color: #4682c0;
  font-size: 2.5rem;
}
</style>
