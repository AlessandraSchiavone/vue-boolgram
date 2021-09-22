<template>
  <div id="app">
    <Nav />
    <main class="container d-flex">
      <Left class="col-lg-8 " />
      <Right class="col-lg-4 px-3" />
    </main>
  </div>
</template>

<script>
import Nav from './components/Nav';
import Left from './components/Left';
import Right from './components/Right';


export default {
  name: 'App',
  components: {
    Nav,
    Left,
    Right
  }
}
</script>

<style lang="scss">

@import './style/general';
main{
  padding-top:120px;
  
}

</style>
