<template>
  <div class="section-right">
    <div class="account d-flex justify-content-between align-items-center">
      <div class="circle-lg"></div>
      <div class="username">
        <h5>alessandra.schiavone</h5>
        <h6><span>Alessandra Schiavone</span></h6>
      </div>
      <div class="premium">
        <a href="#">Passa a </a>
      </div>
      
    </div>
    <div v-if="loading" class="hints">
      <div class="text d-flex justify-content-between align-items-center">
        <h5><span>Suggerimenti per te</span></h5>
        <h5><strong>Mostra tutti</strong></h5>
      </div>
      <div class="single-account d-flex justify-content-between align-items-center my-3"
      v-for="account,index in accounts"
      :key="index">
        <div class="info-account d-flex align-items-center">
          <div class="circle-md "><img :src="account.profile_picture" alt=""></div>
          <div class="name-account mx-3"><strong>{{ account.profile_name}}</strong></div>
        </div>
        <div class="follow">
          <a href="#">Segui</a>
        </div>
      </div>
    </div> 
    <div v-else class="hints">
       <div class="text d-flex justify-content-between align-items-center">
        <h5><span>Suggerimenti per te</span></h5>
        <h5><strong>Mostra tutti</strong></h5>
      </div>
      <HintSkeleton />
    </div>
    <div class="footer">
      <h6><span>&copy; 2021 Instagram from facebook</span></h6>
      </div>  
  </div>
</template>

<script>
import axios from 'axios';
import HintSkeleton from './Skeleton/HintSkeleton';
export default {
  name:"Right",
  components: {
    HintSkeleton
  },
  data: function (){
    return{
      apiUrl:'https://flynn.boolean.careers/exercises/api/boolgram/profiles',
      accounts:[],
      loading:false,
    }
  },
  created:function(){
    setTimeout(() =>
    axios
      .get(this.apiUrl)
      .then(
        (response) =>{
          this.accounts = response.data;
          this.loading=true;
        }
      )
      .catch(), 2000 )
    
  }

}
</script>

<style lang="scss" scoped>
.section-right{
  span{
    color:grey;
  }
  a{
    text-decoration:none;
    color:#0095F6; 
    font-weight:600;
  }
  .account{
    height:70px;
    .circle-lg{
      width:70px;
      height:70px;
      border-radius:50%;
      background-image: url(../assets/profile.jpg);
      background-size: contain;
      &:hover{
          cursor:pointer;
      }
    }
    .username{
      h6 > span{
        font-weight:400;
      }
    }
  }
  .hints{
    margin-top:70px;
    .text{
      h5{
        font-size:16px;
      }
    }
    .circle-md{
      width:40px;
      height:40px;
      img{
        width:40px;
        height:40px;
        object-fit: cover;
        border-radius:50%;
        height:100%;
      }
    }
  }
  .footer{
    margin-top:40px;
    h6{
      text-transform: uppercase;
      font-weight: 300;
    }
  }
  
  
}
</style>