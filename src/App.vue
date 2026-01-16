<template>
  <div class="body">
    <p class="text">我已经想好了一个你绝对猜不到的数</p>
    <input v-model="num" type="text" class="input-box" placeholder="给出你的答案">
    <button @click="add" class="bin">提交</button>
    <div class="hd">
      <p class="text">{{ num2 }}</p>
    </div>
  </div>


</template>

<script setup>
  import {ref}from 'vue'
  const num=ref('')
  const num2=ref('')
  const dan=ref(0)
  dan.value=Math.floor(Math.random()*100)+1
  function add(){
    if(num.value<dan.value){
      num2.value="这么小给黑猪针灸呢？"
    }
    if(num.value>dan.value){
      num2.value="这么大想艹死黑猪吗！"
    }
    if(num.value==dan.value){
      num2.value="你tmd真是个天才"
    }
    num.value=''
  }

</script>

<style scoped>
  .body{
    background:linear-gradient(135deg,#667eea 0%,#764ba2 100%);
    min-height: 100vh;
    width: 200vh;
    display:flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 20px;
  }
  .text{
    font-size: 24px;
    font-weight: bold;
    color: white;
  }
  .input-box{
    width: 300px;
    padding: 12px;
    border: none;
    border-radius: 8px;
    font-size: 16px;
  }
  .bin{
    padding: 12px 40px;
    background-color: #ff6b6b;
    color: white;
    border-radius: 8px;
    font-size: 18px;
    cursor: pointer;
  }

</style>
