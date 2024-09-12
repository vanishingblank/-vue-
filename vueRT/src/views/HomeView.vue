<script >
export default{
  data(){
    return {
      planet:'',
      picPath: ['',"../../pic/1.png",
      "../../pic/2.png",
      "../../pic/3.png",
      "../../pic/4.png",
      "../../pic/5.png",
      "../../pic/6.png",
      "../../pic/7.png",
      "../../pic/8.png",
      "../../pic/9.png",
      "../../pic/10.png",],
    }
  }
}
</script>

<template>
  <main>
    <h1>探索宇宙</h1>
    <div class="choose">
    <select v-model="planet">
      <option value="0"></option>
      <option value="1">水星</option>
      <option value="2">金星</option>
      <option value="3">流星</option>
      <option value="4">月亮</option>
      <option value="5">火星</option>
      <option value="6">土星</option>
      <option value="7">太阳</option>
      <option value="8">木星</option>
      <option value="9">黑洞</option>
      <option value="10">地球</option>
    </select>
    </div>
    <img v-bind:src="picPath[planet]" class="cos"/>
  </main>
</template>
<style>
.choose{
  position:absolute;
  top:150px;

}
.cos{
  position:absolute;
  top:60px;
  left:200px;
  max-width: 300px;
  height:auto;
}

</style>