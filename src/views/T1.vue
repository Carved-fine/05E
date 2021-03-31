<template>
  <div>
    <h1>考试题1、一周任务计划表</h1>
    <!--  -->
    <table>
      <!-- 表头 -->
      <tr>
        <div>周一</div>
        <div>周二</div>
        <div>周三</div>
        <div>周四</div>
        <div>周五</div>
        <div>周六</div>
        <div>周日</div>
      </tr>
      <!-- 中间表格内容 -->
      <tr style="border: 1px solid">
        <div @click="flag = !flag">
          <p v-for="(item, key) in ghq_list" :key="key">
            {{ item.value }}
          </p>
        </div>
        <div @click="flag = !flag"></div>
        <div @click="flag = !flag"></div>
        <div @click="flag = !flag"></div>
        <div @click="flag = !flag"></div>
        <div @click="flag = !flag"></div>
        <div @click="flag = !flag"></div>
      </tr>
    </table>
  <!-- 弹出框的显示部分 -->
    <div class="ghq_box" v-show="flag == true">
      <button @click="flag = false">关闭</button>
      <ul>
        <li v-for="(item, key) in ghq_list" :key="key">
          <button @click="ghq_list.splice(key, 1)">删除</button>
        </li>
      </ul>
      <input type="text" v-model="con" /><button
        @click="ghq_list.push({ 'value': this.con })"
      >
        添加
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      con: "",
      flag: false,
      ghq_list: [{ value: "111" }],
    };
  },
  created() {},
  mounted() {},
  methods: {
    // ghq_add() {
    //   this.ghq_list.push({'value':con});
    // },
  },
};
</script>

<style>
table > tr {
  display: flex;
  background: #ccc;
}
table > tr > div {
  width: 100px;
  height: 100px;
  background: #ccc;
  /* border:1px solid; */
  text-align: center;
}
/* table > tr > div > p {
  width: 100px;
  height: 30px;
  background: red;
  border:1px solid;
  text-align: center;
} */
.ghq_box {
  width: 500px;
  height: 300px;
  background: #fff;
  box-shadow: 10px 12px 16px 8px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
input {
  outline: none;
}
ul {
  list-style: none;
}
</style>


