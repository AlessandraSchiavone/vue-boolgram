<template>
  <div class="story-grey d-flex flex-row align-items-center mt-2">
      <div v-for="n in 5"
      :key="n" class="circle-lg "></div>
  </div>
</template>

<script>
export default {
    name:"StorySkeleton"
}
</script>

<style lang="scss" scoped>
.circle-lg{
  width:70px;
  height:70px;
  margin:0px 10px;
  border-radius:50%;
  background-color: rgb(235, 233, 233);
  border:1px solid lightgray;
}

</style>