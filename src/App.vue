<template>
  <div v-if="show">
    <ul v-for="(book, index) in books" :key="index">
      <li>
        <p>Title: {{ book.title }}</p>
        <p>Author: {{ author }}</p>
        <p>Year: {{ releasing_year }}</p>
        <img :src="book.img" :alt="book.title">
      </li>
    </ul>
  </div>
  <div>
    <button @click="showBooks">
      <span v-if="show"> Hide Books </span>
      <span v-else>Show Books</span>
    </button>
    <button
      @click="
        changeBook({
          title: 'Game of thrones',
          author: 'Jamey Vardy',
          releasing_year: '2009',
        })
      "
    >
      Change Books
    </button>
  </div>
  <div>
    <h1>Mouse Events</h1>
    <div>
      <div class="box" @mouseover="callEvent($event, 5)">MouseOver</div>
      <div class="box" @mouseleave="callEvent($event, 6)">Mouse Leave</div>
      <div class="box" @dblclick="callEvent($event, 7)">Mouse double click</div>
      <div class="box" @mousemove="handleMouseMove">
        Position- {{ x }} {{ y }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      url: "https://google.com",
      title: "Harry Potter",
      author: "J.K Rowling",
      releasing_year: "1995",
      show: true,
      x: 0,
      y: 0,
      books: [
        {
          title: "Name of the wind",
          author: "Patric Rothfuss",
          releasing_year: 2009,
          img: require('@/assets/1.jpg'),
        },
        {
          title: "God of war",
          author: "Ryan Rudolf",
          releasing_year: 2010,
          img: require("@/assets/2.jpg"),
        },
        {
          title: "Proxy Server",
          author: "Patric Rothfuss",
          releasing_year: 2011,
          img: require("@/assets/3.jpg"),
        },
      ],
    };
  },
  methods: {
    showBooks() {
      this.show = !this.show;
    },
    changeBook(data) {
      this.title = data.title;
      this.author = data.author;
      this.releasing_year = data.releasing_year;
    },
    callEvent(e, num) {
      console.log(e);
      console.log(num);
    },
    handleMouseMove(e) {
      this.x = e.offsetX;
      this.y = e.offsetY;
    },
  },
};
</script>

<style>
body {
  background: #eee;
  max-width: 960px;
  margin: 20px auto;
}
h1 {
  color: burlywood;
}
.box {
  padding: 100px 0;
  width: 400px;
  display: inline-block;
  background: #ddd;
  text-align: center;
  margin: 20px;
}
</style>
