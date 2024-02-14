<template>

<div class="timeline custom-bg-color">

    <div class="container left-container">
        <img src="../assets/coolpick2.png">
        <div class="text-box">
            <h2>Alphabet Inc</h2>
            <small> 2018-2019</small>
            <p>Succès dezakndoiznrkejndzlekbfvchk abejlézkdqjevhkzajldnbesjfehbdsdopqlefnljkb
            </p>
            <span class="left-container-arrow"></span>
        </div>
    </div>

    <div class="container right-container">
        <img src="../assets/teamupnow.png">
        <div class="text-box">
            <h2>Alphabet Inc</h2>
            <small> 2018-2019</small>
            <p>Succès dezakndoiznrkejndzlekbfv chkabejlézkdqjevhkzajldnbesjfehbdsdopqlefnljkb
            </p>
            <span class="right-container-arrow"></span>
        </div>
    </div>

    <div class="container left-container">
        <img src="../assets/train.png">
        <div class="text-box">
            <h2>Alphabet Inc</h2>
            <small> 2018-2019</small>
            <p>Succès dezakndoiznrkejndzlekbf vchkabejlézkdqjevhkzajldnbesjfehbdsdopqlefnljkb
            </p>
            <span class="left-container-arrow"></span>
        </div>
    </div>


</div>


</template>
  

  
 
 
 
 <style scoped>
 .body{
    background-color: #746868;
 }

.timeline{
    position : relative;
    max-width: 1200px;
    margin: 100px auto;
}
.container{
    padding : 10px 50px;
    position : relative;
    width : 50%;
    animation: movedown 1s linear forwards;
    opacity: 0;
}
@keyframes movedown{
    0%{
        opacity: 1;
        transform: translateY(-30px);
    }
    100%{
        opacity: 1;
        transform: translateY(0px);
    }
}

.container:nth-child(1){
    animation-delay : 0s
}
.container:nth-child(2){
    animation-delay : 1s
}
.container:nth-child(3){
    animation-delay : 2s
}


.text-box{
    padding : 20px 30px;
    background : #fff;
    position: relative;
    border-radius : 6px;
    font-size : 15px;
}

.left-container{
    left:0;
}
.right-container{
    left:50%
}
.container img{
    position: absolute;
    width:40px;
    border-radius: 50%;
    right: -20px;
    top: 32px;
    z-index: 10;
}
.right-container img{
    left: -20px;
}

.timeline::after{
    content: '';
    position: absolute;
    width:6px;
    height: 100%;
    background: #fff;
    top:0;
    left:50%;
    margin-left: -3px;
    z-index: 2;
    animation:moveline 3s linear forwards;
}

@keyframes moveline{
    0%{
        height: 0;
    }
    100%{
        height: 100%;
    }
}

.text-box h2{
    font-weight: 600;
}
.text-box small{
    display: inline-block;
    margin-bottom: 15px;
}
.custom-bg-color {
  background-color: #000956;
}

.left-container-arrow{
    height: 0;
    width: 0;
    position: absolute;
    top:28px;
    z-index: 1;
    border-top: 15px solid transparent;
    border-bottom: 15px solid transparent;
    border-left: 15px solid white;
    right: -15px;

}
.right-container-arrow{
    height: 0;
    width: 0;
    position: absolute;
    top:28px;
    z-index: 1;
    border-top: 15px solid transparent;
    border-bottom: 15px solid transparent;
    border-right: 15px solid white;
    left: -15px;

}



@media screen and (max-width:600px){
    .timeline{
        margin: 50px auto;
    }
    .timeline::after{
        left: 30px;
    }
    .container{
        width: 100%;
        padding-left: 80px;
        padding-right: 25px;
    }
    .text-box{
        font-size : 13px;
    }
    .text-box small{
        margin-bottom: 10px;
    }
    .right-container{
        left:0;
    }
    .left-container img, .right-container img{
        left: 10px;
    }
    .left-container-arrow, .right-container-arrow{
        border-right: 15px solid #fff;
        border-left : 0;
        left: -15px;
    }
}

  </style>

    <script lang="ts">
    import { defineComponent} from 'vue';
    
    export default defineComponent({
      name: 'Timeline',
    });
    </script>