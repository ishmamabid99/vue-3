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
      <form class="form">
        <input
          maxlength="6"
          class="form-input"
          type="text"
          placeholder="Please Enter Username"
        />
        <input
          maxlength="6"
          class="form-input"
          type="password"
          placeholder="Please Enter Password"
        />
        <button class="login-button" type="submit">LOGIN</button>
      </form>
    </FormModal>
  </div>
</template>

<script>
import FormModal from "./FormModal";
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
  components: { FormModal },
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
.form {
  margin: 10rem 3rem;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.login-title {
  color: #4682c0;
  font-size: 2.5rem;
}
.form-input {
  width: 80%;
  padding: 0rem 2rem;
  border: 1px solid #4682c0;
  height: 3rem;
  margin-top: 1.5rem;
  border-radius: 10px;
  border-color: #4682c0;
}
.login-button {
  color: white;
  font-size: medium;
  background: #4682c0;
  border: none;
  border-radius: 10px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
  height: 3rem;
  width: 80%;
  margin-top: 4rem;
  cursor: pointer;
}
.login-button:active {
  transform: translateY(4px);
}
</style>
