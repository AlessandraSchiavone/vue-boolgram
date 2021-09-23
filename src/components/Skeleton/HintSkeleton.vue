<template>
  <div class="info-account d-flex flex-column  my-3">
        <div class=" d-flex align-items-center mb-2"
         v-for="n in 10"
        :key="n">
        <div class="circle-md "></div>
        <div class="d-flex flex-column ps-2">
        <div class="ret-1 mb-1"></div>
        <div class="ret-2"></div>
        </div>
        
        </div>
    </div>
</template>

<script>
export default {
    name:"HintSkeleton"
}
</script>

<style lang="scss" scoped>
.circle-md{
    width:40px;
    height:40px;
    border-radius:50%;
    background-color: rgb(240, 238, 238);
    border:1px solid lightgray;
    }
    .ret-1{
        width:150px;
        height:10px;
        background: linear-gradient(to right,rgb(240, 238, 238),rgb(253, 251, 251));
    }
    .ret-2{
        width:70px;
        height:10px;
        background:linear-gradient(to right,rgb(240, 238, 238),rgb(253, 251, 251)) ;
    }
</style>