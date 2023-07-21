<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal">
      <div class="left-view">
        <img class="image" :src="svg" />
      </div>
      <div class="right-view">
        <slot name="title"></slot>
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["svgImage"],
  data() {
    return {
      svg: this.svgImage,
    };
  },
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style>
.image {
  width: 100%;
  height: 40rem;
}
.modal {
  display: flex;
  flex-direction: row;
  width: 55rem;
  height: 40rem;
  margin: 10rem auto;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
  background: white;
}
.left-view {
  width: 27.5rem;
  flex-grow: 1;
}
.right-view {
  width: 27.5rem;
  flex-grow: 1;
  flex-direction: row;
}
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  z-index: 10;
  height: 100%;
}
</style>
