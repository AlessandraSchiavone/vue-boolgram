<template>
  <div id="app">
    <Nav />
    <main class="container ">
      <div class="row d-flex">
        <Left class="col-lg-7" />
        <Right class="col-lg-4 offset-lg-1" />
      </div>
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
