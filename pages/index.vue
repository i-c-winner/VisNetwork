<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">
        front_semantic
      </h1>
      <div class="links">
        <a
          href="https://nuxtjs.org/"
          target="_blank"
          rel="noopener noreferrer"
          class="button--green"
        >
          Documentation
        </a>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          rel="noopener noreferrer"
          class="button--grey"
        >
          GitHub
        </a>
      </div>
    </div>
    <body>
      <div id="app">
        <network ref="network" :nodes="nodes" :edges="edges" :options="options">
        </network>
      </div>
    </body>
  </div>
</template>

<script>
import Vue from "vue";
import { Network } from "vue-vis-network";
console.log(Network);
const visNetwork = new Vue({
  el: "#app",
  data() {
    return {
      nodes: [
        { id: 1, label: "circle", shape: "circle" },
        { id: 2, label: "ellipse", shape: "ellipse" },
        { id: 3, label: "database", shape: "database" },
        { id: 4, label: "box", shape: "box" },
        { id: 5, label: "diamond", shape: "diamond" },
        { id: 6, label: "dot", shape: "dot" },
        { id: 7, label: "square", shape: "square" },
        { id: 8, label: "triangle", shape: "triangle" }
      ],
      edges: [
        { from: 1, to: 2 },
        { from: 2, to: 3 },
        { from: 2, to: 4 },
        { from: 2, to: 5 },
        { from: 5, to: 6 },
        { from: 5, to: 7 },
        { from: 6, to: 8 }
      ],
      options: {
        nodes: {
          borderWidth: 4
        },
        edges: {
          color: "lightgray"
        }
      }
    };
  }
});

export default {
  components: { Network }
};
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
