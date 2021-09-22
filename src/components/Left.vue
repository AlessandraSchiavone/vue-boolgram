<template>
<div class="section-left pe-5">
    <div class="stories d-flex justify-content-around align-items-center p-5">
        <Story
        v-for="account,index in accounts"
        :key="index" 
        :item="account"
        />
    </div>
    <div class="posts">
        <Post />
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
      apiUrl:'https://flynn.boolean.careers/exercises/api/boolgram/profiles',
      accounts:[],
      
    }
  },
   created:function(){
    axios
      .get(this.apiUrl)
      .then(
        (response) =>{
          console.log(response.data);
          this.accounts = response.data.slice(0,6);
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