<template>
<div class="section-left ">
    <div class="stories d-flex justify-content-around align-items-center p-5">
        <Story
        v-for="account,index in accounts"
        :key="index" 
        :item="account"
        />
    </div>
    <div class="posts my-5"
      >
      <Post 
      v-for="post,index in posts"
      :key="index"
      :item="post"
      />
    </div>    
</div>
    

  
</template>

<script>
import Story from './Story';
import Post from './Post';
import axios from 'axios';

export default {
    name: 'Left',
    components: {
        Story,
        Post,
  },
  data: function (){
    return{
      firstapiUrl:'https://flynn.boolean.careers/exercises/api/boolgram/profiles',
      secondapiUrl:'https://flynn.boolean.careers/exercises/api/boolgram/posts',
      accounts:[],
      posts:[]
      
    }
  },
   created:function(){
    axios
      .get(this.firstapiUrl)
      .then(
        (response) =>{
          // console.log(response.data);
          this.accounts = response.data.slice(0,6);
        }
      )
      .catch();
    axios
      .get(this.secondapiUrl)
      .then(
        (response) =>{
          this.posts = response.data;
          // console.log(this.posts);    
        }
      )
      .catch();
  }
}
</script>

<style lang="scss" scoped>
.section-left{
    .stories{
        height:150px;
        border:1px solid lightgrey;
        margin: 0 auto;
    }
}

</style>