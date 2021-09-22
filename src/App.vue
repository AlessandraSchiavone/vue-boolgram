<template>
  <div id="app">
    <Nav />
    <main>
      <Left />
      <Right />
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

</style>
