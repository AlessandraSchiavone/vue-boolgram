<template>
<div class="section-left ">
    <div v-if="loading" >
    <div class="stories d-flex justify-content-around align-items-center p-5">
      <Story
      v-for="account,index in accounts"
      :key="index" 
      :item="account"
      />
    </div>
    <div class="posts my-5">
      <Post 
      v-for="post,index in posts"
      :key="index"
      :item="post"
      />
    </div>
    </div>
    <div v-else-if="!loading" >
      <div class="stories d-flex flex-column p-3">
        <img class="loader align-self-center" src="../assets/spinner.gif" >
        <StorySkeleton />
      </div> 
      <div class="posts my-5">
        <PostSkeleton/>
    </div>
    </div>
        
</div>
    

  
</template>

<script>
import Story from './Story';
import StorySkeleton from './Skeleton/StorySkeleton';
import Post from './Post';
import PostSkeleton from './Skeleton/PostSkeleton';
import axios from 'axios';

export default {
    name: 'Left',
    components: {
        Story,
        Post,
        StorySkeleton,
        PostSkeleton
  },
  data: function (){
    return{
      firstapiUrl:'https://flynn.boolean.careers/exercises/api/boolgram/profiles',
      secondapiUrl:'https://flynn.boolean.careers/exercises/api/boolgram/posts',
      loading:false,
      accounts:[],
      posts:[]
      
    }
  },
  created:function(){
    setTimeout(() => {
    axios
      .get(this.firstapiUrl)
      .then(
        (response) =>{
          // console.log(response.data);
          this.accounts = response.data.slice(0,6);
          this.loading=true;
        }
      )
      .catch();
      axios
        .get(this.secondapiUrl)
        .then(
          (response) =>{
            this.posts = response.data;
            this.loading=true;
            // console.log(this.posts);    
          }
        )
        .catch();  
      },2000)

         
  }
}
</script>

<style lang="scss" scoped>
.section-left{
    .stories{
        height:150px;
        border:1px solid lightgrey;
        margin: 0 auto;
        .loader{
          text-align:center;
          width:40px;
        }
    }
}

</style>