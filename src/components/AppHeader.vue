<template>
  <nav class="navbar">
    <div class="logo" >
      <img :src="logo" />
    </div>
    <div class="options">
      <p class="nav-items" v-for="(item, index) in options" :key="index">
        {{ item }}
      </p>
    </div>
  </nav>
  <FormModal/>
</template>

<script>
import FormModal from "./FormModal";
import logo from "../assets/logo.png";
export default {
  props: ["options"],
  data() {
    return {
      logo: logo,
    };
  },
  components:{FormModal}
};
</script>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
}
.options {
  margin-right: 30px;
  display: flex;
  flex-direction: row-reverse;
}
.nav-items {
  margin-right:50px;
  color:#4682c0;
  cursor: pointer;
  font-size: 1.35rem;
  font-weight: 600;
}
.logo {
  margin-left: 30px;
}
.logo img{
  width: 250px;
}
</style>
