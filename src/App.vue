<template>
  <Header></Header>
  <ProductTable></ProductTable>
 </template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue';
import ProductTable from './components/ProductTable.vue';

export default {
    name: "App",
    data() {
        return {
            title: "MEETOPTICS App"
        };
    },
    methods: {
        handleClick() {
            console.log(this.$refs.titless);
        }
    },
    components: { Header, ProductTable }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
  margin-bottom: 0vh;
  background-color: #ccc;
}
</style>
