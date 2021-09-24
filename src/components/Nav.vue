<template>
    <header>
        <div class="nav container d-flex justify-content-between align-items-center">
            <div class="logo">
                <img src="../assets/logo.png" alt="Logo Boolgram">
            </div>
            <div class="search "> Cerca </div>
            <div class="info-account d-flex justify-content-around align-items-center">
                <i class="far fa-heart mx-2"></i>
                <i class="fas fa-home  mx-2 "></i>
                <div class="circle text-center mx-2"></div>
            </div>  
        </div>    
    </header>   
       
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
header{
    height:60px;
    width:100%;
    z-index:1;
    background-color: white;
    border-bottom:1px solid lightgrey;
    position:fixed;
    top:0;
    left:0; 
    .nav{
        height:100%;
        .logo{
            img{
               height:35px;    
            }
            &:hover{
                    cursor:pointer;
                } 
        }
        .search{
           border: 1px solid lightgrey;
           padding:2px 80px;
           color:grey;
           font-weight: 500;
        }
        .info-account{
            i{
                font-size:22px;
                &:hover{
                    cursor:pointer;
                }
            }
            .circle{
                width:40px;
                height:40px;
                border-radius:50%;
                background-image: url(../assets/profile.jpg);
                background-size: contain;
                &:hover{
                    cursor:pointer;
                }
            }
        }
    }  
}
</style>