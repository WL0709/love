<template>
  <div class="container">

    <div class="external">
      <div v-if="sizeNum===0" style=" text-align: center; ">
        <h1>!!!喜欢你!! ( >᎑<)♡︎ᐝ</h1>
        <img src="../assets/hug.png">

      </div>
      <div v-else>
        <div class="top">
          <img src="../assets/heart.png" v-if="sizeNum===1" class="image">
          <img src="../assets/shocked.png" v-if="sizeNum===1.5" class="image">
          <img src="../assets/think.png" v-if="sizeNum===2" class="image">
          <img src="../assets/angry.png" v-if="sizeNum===2.5" class="image">
          <img src="../assets/crying.png" v-if="sizeNum>=3" class="image">
          <h1>可以成为我的恋人吗？</h1>
        </div>
        <div class="bottom">
          <el-button  type="primary"  :style="confirm" @click="sizeNum=0">同意</el-button>
          <el-button type="danger" style="margin-left: 10%"  v-if="sizeNum===1" @click="ChangeSize"> 不要</el-button>
          <el-button type="danger" style="margin-left: 10%"  v-if="sizeNum===1.5" @click="ChangeSize"> ？你认真的吗…</el-button>
          <el-button type="danger" style="margin-left: 10%"  v-if="sizeNum===2" @click="ChangeSize"> 要不再想想？</el-button>
          <el-button type="danger" style="margin-left: 10%"  v-if="sizeNum===2.5" @click="ChangeSize"> 不许选这个！ </el-button>
          <el-button type="danger" style="margin-left: 10%"  v-if="sizeNum>=3" @click="ChangeSize"> 我会很伤心…</el-button>

        </div>

      </div>

    </div>

  </div>

</template>

<script  >
export default {
  data() {
    return {
      sizeNum:1,
      confirm: {
        transform: 'scale(1)'
      },
    };
  },
  methods: {
    ChangeSize() {
      this.sizeNum=this.sizeNum+0.5
      console.log(this.sizeNum)
      this.confirm.transform = "scale("+this.sizeNum+")";

    },
  },
};

</script>
<style scoped>
.image{
  width: 200px;
  height: 200px;
}
.external{
  width: 50%; /* 设置宽度 */
  height: 50%; /* 设置高度 */
  display: flex; /* 使用 Flexbox 布局 */
  flex-direction: column; /* 垂直排列子元素 */
  justify-content: space-between; /* 子元素在容器中上下分布 */
}
.container {
  display: flex;
  justify-content: center; /* 水平居中 */
  align-items: center;    /* 垂直居中 */
  height: 100vh;          /* 使容器高度为视口的100% */
 background: #f1d5da;
}
.top{

  padding: 10px; /* 内边距 */
  text-align: center; /* 文字居中 */
}
.bottom{

  padding: 10px; /* 内边距 */
  text-align: center; /* 文字居中 */
}
</style>
