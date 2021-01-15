<template>
  <a-layout id="components-layout-demo-top" class="layout">
    <a-layout-header>
      <div class="logo" />
      <a-menu
        theme="dark"
        mode="horizontal"
        :defaultSelectedKeys="['2']"
        :style="{ lineHeight: '64px',background: 'darkblue'}"
      >
        <a-menu-item key="1" @click="onclick('西电')" style="color:red">学校概况</a-menu-item>
        <a-menu-item key="2" @click="onclick('南航')" style="color:blue">师资力量</a-menu-item>
        <a-menu-item key="3" @click="get()" style="color:cyan">招生就业</a-menu-item>
      </a-menu>
    </a-layout-header>
    <a-layout-content style="padding: 0 50px">
      <a-breadcrumb style="margin: 16px 0">
        <a-breadcrumb-item>Home</a-breadcrumb-item>
        <a-breadcrumb-item>List</a-breadcrumb-item>
        <a-breadcrumb-item>App</a-breadcrumb-item>
      </a-breadcrumb>
      <div :style="{ background: 'yellow', padding: '24px', minHeight: '480px' }">{{msg}}</div>
    </a-layout-content>
    <a-layout-footer style="text-align: center">皇马俱乐部 ©2021 Created by 皇家马德里</a-layout-footer>
  </a-layout>
</template>


<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      msg: "Welcome to Your Vue.js App"
    };
  },
  methods: {
    onclick(param) {
	   this.msg=param+' 前端第一次使用antd'
      console.log(123);
    },
	get() {       
		this.$axios({        

		  method: 'get',        

		  url: 'http://localhost:9003/test/first',

		  data: {}

		 }).then((result) => {         
		   console.log("请求结：")      
		   console.log(result)
           this.msg=result.data.number		   

		 })     
    }  
	
	
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
