<template>
  <div class="hello">
    <input type="text" v-on:input="messageChange">
    <h1>{{ msg }}</h1>
      <Attributes />
  </div>
</template>

<script>
import Attributes from './Attributes.vue'
export default {
  name: "HelloWorld",
   components: {
    Attributes
  },
  props: {
    msg: String,
  },
  methods:{
    messageChange(event){
    this.msg=event.target.value;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
