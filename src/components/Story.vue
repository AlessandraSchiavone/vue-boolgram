<template>
  <div class="single-story d-flex flex-column align-items-center">
    <div class="circle-lg"><img :src="item.profile_picture" alt=""></div>
    <div class="name pt-2">{{ truncateName(item.profile_name)}}</div>
  </div>
</template>

<script>
export default {
    name:'Story',
    props: [ "item" ],
    methods: {
      truncateName: function(string, charsNumber = 10) {
        if(string.length > charsNumber) {
          return string.substr(0, charsNumber) + '...';
        } else {
          return string;
        }
      }
    }
}
</script>

<style lang="scss" scoped>
.circle-lg{
  width:80px;
  height:80px;
  img{
    width:80px;
    height:80px;
    border-radius:50%;
    padding:2px;
    border:3px solid #c72b52;
    height:100%;
    &:hover{
      cursor:pointer;
    }
  }
}
</style>