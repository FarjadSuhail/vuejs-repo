<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" /> -->
    Hello {{ name }}
    <div v-text="channel"></div>
    <div v-html="channel"></div>
    <h2 v-bind="heading">Heading</h2>
    <button v-bind:disabled="isDisabled">Bind</button>

    <h2 class="underline">Underline</h2>
    <h2 class="underline" v-bind:class="status">Status</h2>

    <h2 v-bind:class="isPromoted && 'promoted'">Promoted Movie</h2>
    <h2 v-bind:class="{ new: isSoldOut, 'sold-out': !isSoldOut }">
      SoldOut? Movie
    </h2>

    <h2 v-bind:class="['new', 'promoted']">Newly Pormoted Movies</h2>
    <h2
      v-bind:class="[isPromoted && 'promoted', isSoldOut ? 'new' : 'sold-out']"
    >
      Array Conditional Movies
    </h2>

    <h2
      v-bind:class="{
        promoted: isPromoted,
        new: !isSoldOut,
        'sold-out': isSoldOut,
      }"
    >
      Object Conditional Movies
    </h2>
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  data() {
    return {
      greet: "Greetings",
      name: "Learning VueJS",
      channel: "<b>Coding</b>",
      headingId: "heading",
      isDisabled: true,
      status: "danger",
      isPromoted: false,
      isSoldOut: false,
    };
  },
  components: {
    // HelloWorld,
  },
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

.underline {
  text-decoration: underline;
}

.danger {
  color: red;
}

.promoted {
  font-style: italic;
}

.new {
  color: green;
}
.sold-out {
  color: blue;
}
</style>
