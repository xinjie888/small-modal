# Modal 组件
基于vue2.0的弹窗组件
支持标题、正文、按钮的自定义
### 安装
```
npm install -D small-modal
```
### 使用
```
import Modal from 'Modal'
Vue.component(Modal.name, Modal)
```
### 参数说明
* btnQx
> 是否显示取消按钮
* btnOk
> 是否显示确定按钮
* showButton
> 是否显示组件内置按钮。默认为true
* title
> 标题文案
* msg
> 正文文案

```
<template>
  <div class="page-more">
    <div style = "color:#FFF;font-size:14px;background-color:#000;">
      <Modal @isModal="myModal" v-show="a" :parameter="myParm"></Modal>
    </div>
    <button @click="myClick">弹出窗口</button>
  </div>
</template>

<script>
  export default {
    name: 'ellipsis',
    data() {
      return {
	a:false,
	myParm:{
        btnQx:true,
        btnOk:true,
        title:"提示",
        msg:"确定执行此操作？"
      }
      }
    },
    created() {
      
    },
    methods: {
     myClick(){
        console.log(this.a);
        this.a=!this.a;
      },
       myModal(msg){
        console.log(msg);
       this.a=msg;
     }
    }
  }
</script>
```
