<template>
  <div class="calculator">
    <div id="app">
      <div class="results">
          <input class="input" v-model="currentInput">
      </div>
      <button class="button" v-on:click="press">7</button>
      <button class="button" v-on:click="press">8</button>
      <button class="button" v-on:click="press">9</button>
      <button class="button" v-on:click="press">4</button>
      <button class="button" v-on:click="press">5</button>
      <button class="button" v-on:click="press">6</button>
      <button class="button" v-on:click="press">1</button>
      <button class="button" v-on:click="press">2</button>
      <button class="button" v-on:click="press">3</button>
      <button class="button" v-on:click="press">+</button>
      <button class="button" v-on:click="press">-</button>
      <button class="button" v-on:click="press">C</button>
      <button class="button" v-on:click="press">*</button>
      <button class="button" v-on:click="press">/</button>
      <button class="button" v-on:click="press">.</button>
      <button class="button" v-on:click="press">&#60;=</button>
      <button class="button" v-on:click="press">=</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      currentInput: "",
    }
  },
  methods: {
    press (event) {
    let key = event.target.innerText;
    switch (key) {
      case '=':
        this.currentInput = eval(this.currentInput);
        break;
      case 'C':
        this.currentInput = "";
        break;
      case '.':
        this.currentInput += ".";
        break;
      case '<=':
        this.currentInput = this.currentInput.substring(0, this.currentInput.length - 1);
        break;
      case '+':
        this.currentInput += "+";
        break;
      case '-':
        this.currentInput += "-";
        break;
      case '*':
        this.currentInput += "*";
        break;
      case '/':
        this.currentInput += "/";
        break;
      default:
        this.currentInput += key;
      }
    },
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
.input {
  width: 200px;   height: 50px;
  border-radius: 0px;
  border: 1px solid hsl(0, 0%, 0%);
  background-color: #333333;
  color: #d9d9d9;
  padding: 0 5px 0 5px;
  margin: 0 0px 10px 0px;
  font-size: 30px;
}
.button {
  margin: 3px;
  width: 63px;
  border: 1px solid hsl(0, 0%, 5%);
  height: 25px;
  border-radius: 4px;
  color: hsl(0, 0%, 85%);
  background-color: hsl(0, 0%, 10%);
  cursor: pointer;
  outline: none;
}
.calculator {
  width: 250px;
  padding: 20px;
  border-radius: 5px;
  margin: 12% 30%;
  background-color: hsl(0, 0%, 20%);
}
</style>
