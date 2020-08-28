<template>
  <div id="app">
    <h1>{{currentNum+1}}</h1>
    <img :src="dots[currentNum]" />
    <div class="btnWrapper">
      <div class="btn" @click="minus()">- 1</div>
      <div class="btn" @click="plus()">+1</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      dots: [
        require("./assets/dots/one.png"),
        require("./assets/dots/two.png"),
        require("./assets/dots/three.png"),
        require("./assets/dots/four.png"),
        require("./assets/dots/five.png"),
        require("./assets/dots/six.png"),
        require("./assets/dots/seven.png"),
        require("./assets/dots/eight.png"),
        require("./assets/dots/nine.png"),
        require("./assets/dots/ten.png")
      ],
      currentNum: 0
    };
  },
  created() {
    console.log(this.dots[0]);
    console.log(this.currentNum);
  },
  methods: {
    plus() {
      if (this.currentNum === this.dots.length - 1) {
        return;
      }
      this.currentNum++;
    },
    minus() {
      if (this.currentNum === 0) {
        return;
      }
      this.currentNum--;
    }
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  user-select: none;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 750px;
  padding-top: 2px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
h1 {
  margin: 0;
}
img {
  width: 60%;
  margin: 0 auto;
  border-radius: 5%;
}
#app .btnWrapper {
  width: 25%;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
}
#app .btnWrapper .btn {
  width: 150px;
  height: 70px;
  border-radius: 10px;
  background-color: tomato;
  box-shadow: 0 2.5px 0 rgb(158, 53, 35);
  color: white;
  font-size: 30px;
  line-height: 70px;
  display: inline-block;
}
#app .btnWrapper .btn:hover {
  cursor: pointer;
  opacity: 0.8;
}
#app .btnWrapper .btn:active {
  box-shadow: none;
  position: relative;
  top: 2.5px;
}
</style>
