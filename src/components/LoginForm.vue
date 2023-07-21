<template>
  <form @submit.prevent="handleSubmit" class="form">
    <input
      v-model="username"
      maxlength="6"
      class="form-input"
      type="text"
      placeholder="Please Enter Username"
    />
    <input
      v-model="password"
      maxlength="6"
      class="form-input"
      type="password"
      placeholder="Please Enter Password"
    />
    <button class="login-button" type="submit">LOGIN</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      username: "",
      password: "",
    };
  },
  unmounted() {
    this.username = "";
    this.password = "";
  },
  methods: {
    handleSubmit() {
      console.log(this.username + " " + this.password);
    },
  },
};
</script>

<style>
.form {
  margin: 10rem 3rem;
  display: flex;
  flex-direction: column;
  align-items: center;
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
