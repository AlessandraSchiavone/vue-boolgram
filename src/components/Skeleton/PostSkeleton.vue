<template>
  <div class="single-post mt-5">
      <div class="header d-flex justify-content-between align-items-center">
            <div class="info-account d-flex align-items-center  ">
                <div class="circle-md"></div>
                <div class=" d-flex flex-column px-3">
                    <div class="ret-1"></div>
                    <div class="ret-2 mt-1"></div>
                </div>
            </div>
      </div>
      <div class="main">
      </div>
    </div>
</template>

<script>
export default {
name:"PostSkeleton"
}
</script>

<style lang="scss" scoped>
.single-post{
    height:600px;
    border:1px solid lightgrey;
    .header{
        height:50px;
        padding: 30px 10px;
        .circle-md{
            width:40px;
            height:40px;
            border-radius:50%;
            background-color: rgb(221, 220, 220);
            border:1px solid lightgray;
        }
        .ret-1{
            width:150px;
            height:10px;
            background-color: rgb(221, 220, 220);
        }
        .ret-2{
            width:70px;
            height:10px;
            background-color: rgb(221, 220, 220);
        }
    }
    .main{
        height:calc(100% - 50px);
        background-color: rgb(238, 237, 237);
    }
}

</style>