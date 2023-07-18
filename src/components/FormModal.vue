<template>
  <div>
    <h1>
      {{ header }}
    </h1>
    <p>
      {{ text }}
    </p>
  </div>
</template>

<script>
export default {
  props: ["header", "theme"],
  data() {
    return { title: "This is the modal" };
  },
};
</script>

<style></style>
