<template>
  <div>
    <h1>考试题2、分步表单</h1>
    <!-- 步骤条 -->
    <ul>
      <li @click="act = 1" :class="{ active: 1 }">第一步</li>
      <li @click="act = 2" :class="{ active: 2 }">第二步</li>
      <li @click="act = 3" :class="{ active: 3 }">第三部</li>
      <li @click="act = 4" :class="{ active: 4 }">第四部</li>
    </ul>
    <!-- 显示的手动填充部分 -->
    <div>
      <!-- 填充商品名称 -->
      <p v-show="act == 1">
        <input type="text" id="inp1" placeholder="商品名称" v-model="product.name">
        <button @click="ghqacto" >下一步</button>
      </p>
      <!-- 填充商品价格 -->
      <p v-show="act == 2">
        <input type="text" id="inp2" placeholder="价格" v-model="product.price">
        <button @click="act = 1">上一步</button>
        <button @click="ghqactt">下一步</button>
      </p>
      <!-- 填充商品图片 -->
      <p v-show="act == 3">
        <input type="text" id="inp3" placeholder="图片路径" v-model="product.url">
        <button @click="act = 2">上一步</button>
        <button @click="ghqacth">下一步</button>
      </p>
      <!-- 填充库存量 -->
      <p v-show="act == 4">
        <input type="text" id="inp4" placeholder="库存量" v-model="product.num">
        <button @click="act = 3">上一步</button>
        <button @click="ghqactf">提交</button>
      </p>
      <!-- 最终显示出的商品信息 -->
      <section v-show="act == 5">
        显示
          <span v-for="(item,key) in product" :key="key">商品名称：{{ item }}</span>
          <span v-for="(item,key) in product" :key="key">价格：{{ item.price }}</span>
          <span v-for="(item,key) in product" :key="key">图片路径：{{ item.url }}</span>
          <span v-for="(item,key) in product" :key="key">库存量：{{ item.num }}</span>
        <!-- 清空 -->
          <button @click="product = []">清空</button>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      act: 1,
      product:{
        name:'',
        price:'',
        url:'',
        num:''
      }
    };
  },
  created() {},
  mounted() {},
  methods: {


    ghqacto(){
      if(inp1.value == ''){
        alert('不能为空')
        return
      }
      this.act = 2;
    },
    ghqactt(){
      if(inp2.value == ''){
        alert('不能为空')
        return
      }
      this.act = 3;
    },
    ghqacth(){
      if(inp3.value == ''){
        alert('不能为空')
        return
      }
      this.act = 4;
    },
    ghqactf(){
      if(inp4.value == ''){
        alert('不能为空')
        return
      }
      this.act = 5;
    }
    
  },
};
</script>

<style scoped lang="less">
</style>
