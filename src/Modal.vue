<template>
  <div class="modal">
    <div class="dialog">
      <h3 class="dialog_title">{{parameter.title}}</h3>
      <div class="dialog_text">{{parameter.msg}}</div>
      <div>
        <div class="btn pstQx" @click="quXiao" v-show="parameter.btnQx">取消</div>
        <div class="btn pstOk" @click="queDing" v-show="parameter.btnOk">确定</div>
      </div> 
    </div>   
  </div>  
</template>
<script>
  export default {
  name: 'Modal',
  components:{
    
  },
  props:["parameter"],
  data () {
    return {
      msg: 'fdgfdgdf',
      myqx:false
    }
  },
  methods:{
      quXiao(){
          this.$emit('isModal',this.myqx);
      },
      queDing(){
          this.$router.push('/homepage');
      }
  },
  mounted(){
     
  }
}
</script>
<style>
.modal{
    position:absolute;
    top:0;
    left:0;
    width:100%;
    height:100%;
    background:rgba(0,0,0,.5);
    z-index:10000;
}
.dialog{
    width:80%;
    height:400px;
    border-radius:10px;
    position:absolute;
    top:38%;
    left:10%;
    background:#f4f4f4;
    z-index:10001;
}
.btn{
    display:inline-block;
    width:50%;
    height:80px;
    line-height:80px;
    text-align:center;
    font-size:50px;
    border:0;
    color:#000;
}
.pstOk{
    position:absolute;
    bottom:20px;
    right:0px;
    border-radius:0 0 10px 0;
}
.pstQx{
    position:absolute;
    bottom:20px;
    left:0px;
    border-radius:0 0 0 10px;
}
.dialog_title{
    height:100px;
    line-height:100px;
    font-size:50px;
    text-align:center;
    border-radius:10px 10px 0 0;
    margin:30px 0 0;
    color:#000;
}
.dialog_text{
    height:110px;
    line-height:110px;
    text-align:center;
    font-size:50px;
    color:#999;
}
</style>