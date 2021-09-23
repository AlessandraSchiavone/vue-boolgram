<template>
  <div class="single-post mt-5">
    <div class="header d-flex justify-content-between align-items-center p-3">
      <div class="info-account d-flex align-items-center  ">
        <div class="circle-md">
          <img :src="item.profile_picture" alt="">
        </div>
        <div class="name px-3"><strong>{{ item.profile_fullname}}</strong></div>
      </div>
      <div class="dots">
        <i class="fas fa-ellipsis-h"></i>
      </div>
    </div>
    <div class="main">
      <img :src="item.post_image" alt="">
      <div class="box">
        <div class="actions p-3">
          <i class="pe-2 fa-heart " @click="toggleHeart()" :class="flagheart ? 'fas red' : 'far '"> </i>
          <i class="far fa-comment ps-2"></i>
        </div>
        <div class="likes px-3 d-flex align-items-center "
          v-if="item.likes.length > 0">
          <div class="circle-sm">
            <img :src="item.likes[0].profile_picture" alt="">
          </div>
          <div class="like ps-2" >
            Piace a <strong>{{item.likes[0].username}} </strong>
            <span
            v-if="item.likes.length - 1 > 0 && item.likes.length - 1 != 1 "
            >
              e <strong>{{ item.likes.length - 1}} altri</strong>
            </span>
            <span
            v-else-if="item.likes.length - 1 == 1">
              e <strong>{{ item.likes[1].username }}</strong>
            </span>
          </div>
          
        </div>
        <div class="px-3" v-else>
            Ancora nessun mi piace
        </div>
        <div class="name-post p-3">
          <div class="name-utente pb-2">
            <strong>{{item.profile_name}}</strong>
            <span class="ps-2 ">{{item.post_text}}</span>
          </div>
          <div class="view text-grey " v-if="item.comments.length > 3 && !flagcomment " @click="ViewComment()">Mostra tutti e {{ item.comments.length }} commenti </div>
          <div v-if="!flagcomment">
            <div class="comments "
            v-for="comment,index in item.comments.slice(0,3)"
            :key="index">
            <strong>{{comment.username}}</strong>
            <span class="ps-1">{{comment.text}}</span>
            </div>
          </div>
          <div v-else>
            <div class="comments "
            v-for="comment,index in item.comments"
            :key="index">
            <strong>{{comment.username}}</strong>
            <span class="ps-1">{{comment.text}}</span>
            </div>
          </div>
          
          <div class="hours pt-2">
            <span class="text-grey"> {{differenceDate(item.date.date)}} ore fa </span>
          </div> 
        </div>
        <div class="new-comment p-3 d-flex justify-content-between aling-items-center">
            <div>
              <span class="text-grey">Aggiungi un nuovo commento</span>
              </div>
            <div>
              <a href="">Pubblica</a>
            </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    name:'Post',
    props: [ "item" ],
    data:function(){
    return {
        flagheart: false,
        flagcomment:false,
      }
    },
    methods: {
        toggleHeart: function() {
            this.flagheart = !this.flagheart;
        },
        ViewComment: function() {
            this.flagcomment = !this.flagcomment;
        },
        differenceDate:function(date){
          var oldDate = new Date(date).getTime();
          const today = new Date().getTime();
          var difference = Math.floor((today - oldDate)/ (1000*60*60));
          return difference;
        }
    }
}
</script>

<style lang="scss" scoped>
.single-post{
  border:1px solid lightgrey;
  .info-account{
    .circle-md{
      width:40px;
      height:40px;
      img{
        width:40px;
        height:40px;
        border-radius:50%;
        padding:1px;
        border:2px solid #c72b52;
        height:100%;
        &:hover{
          cursor:pointer;
        }
      }
    }
  }
  .main{
    img{
      width:100%;
      object-fit:contain;
    }
    .text-grey{
        color:grey,
      }
    .box{
      .actions{
        .red{
            color:rgba(221, 11, 11, 0.856);
          }
        i{
          font-size: 25px;
          
          &:hover{
            cursor:pointer;
          }
        }

      }
      .likes{
        .circle-sm{
          width:30px;
          height:30px;
          img{
            width:30px;
            height:30px;
            object-fit: cover;
            border-radius:50%;
            height:100%;
          }
          
        }
      } 
      .view{
        cursor:pointer;
      }
      .new-comment{
        border-top:1px solid lightgrey;
        a{
            text-decoration:none;
            color:#0095F6; 
            font-weight:600;
        }  
      } 
    }
    
  }
}

</style>