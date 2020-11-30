<template>
  <!-- Piano container -->
  <div class="center-box">
    <!-- <h1> Virtual Piano </h1> -->
    <!-- Loop through all the keys -->
    <div class="keyboard">
      <div class="pianokey">
        <div class = "white">
         <WhiteKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "black">
         <BlackKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "white">
         <WhiteKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "black">
         <BlackKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "white">
         <WhiteKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "white">
         <WhiteKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "black">
         <BlackKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "white">
         <WhiteKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "black">
         <BlackKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "white">
         <WhiteKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "black">
         <BlackKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "white">
         <WhiteKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "white">
         <WhiteKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "black">
         <BlackKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "white">
         <WhiteKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "black">
         <BlackKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "white">
         <WhiteKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "white">
         <WhiteKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "black">
         <BlackKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "white">
         <WhiteKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "black">
         <BlackKey />
        </div>
      </div>
       <div class="pianokey">
        <div class = "white">
         <WhiteKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "black">
         <BlackKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "white">
         <WhiteKey />
        </div>
      </div>
      <div class="pianokey">
        <div class = "white">
         <WhiteKey />
        </div>
      </div>
    </div>
  </div>
     
</template>

<script>
import WhiteKey from "./WhiteKey";
import BlackKey from "./BlackKey";
export default {
  name: "Piano",
  components: { WhiteKey, BlackKey },
};
</script>

<style scoped>
.center_box {
    text-align: center;
    position: relative;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    width: 100%;
}

 .keyboard {
    display: inline-block;
    margin-bottom: 30px;
} 

.pianokey {
    display: inline-block;
    position: relative;
    cursor: pointer;
}

.white {
    width: 46px;
    height: 250px;
    border: solid 1px #d0d0d0;
    transform: translate(-3px, -3px);
    transition: 0.1s;

  
}
.black {
    position: relative;
    top: 0;
    width: 30px;
    height: 165px;
    background-color: #000000;
    margin-left: -14px;
    margin-right: -16px;
    z-index: 20;
    transform: translate(-3px, -3px);
    left: 0;
}

div {
    display: inline-block;
    text-align: center;
    left: 20px;
}

</style>