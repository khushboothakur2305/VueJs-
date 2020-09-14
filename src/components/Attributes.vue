<template>
  <div>
      <h1>Section 2</h1>
    <table v-on:mousemove="updateCoordinates">
      <tr>
        <td colspan="5"><h1>Attributes</h1></td>
      </tr>
      <tr>
        <td><h1>v-bind</h1></td>
        <td><h1>v-once</h1></td>
        <td><h1>v-html</h1></td>
        <td><h1>v-on Click</h1></td>
        <td><h1>v-on Mouse Move</h1></td>
      </tr>
      <tr>
        <th><a v-bind:href="link">Google</a></th>
        <th>
          <h2 v-once>{{ title }}</h2>
          <p>{{ sayHello() }}</p>
        </th>
        <th><p v-html="finishedLink"></p></th>
        <th>
          <button v-on:click="increase(2)">Click Me!!</button>
          <p>{{ Counter }}</p>
        </th>
        <th>
          <p>Coordinates:{{ x }}/{{ y }}</p>
        </th>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: "Attributes",
  props: {},
  data() {
    return {
      link: "http://google.com",
      title: "Hello World !!",
      finishedLink: '<a href="http://google.com">Google</a>',
      Counter: 0,
      x: 0,
      y: 0,
    };
  },
  methods: {
    sayHello() {
      this.title = "Hello";
      return this.title;
    },
    increase(step) {
      this.Counter += step;
    },
    updateCoordinates(event) {
      (this.x = event.clientX), (this.y = event.clientY);
    },
  },
};
</script>

<style scoped>
a {
  color: #42b983;
}
h1{
    text-align: center;
}

td {
    text-align: center;
  width: 260px;
}
</style>
