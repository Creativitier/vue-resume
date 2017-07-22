<template>
  <div id="toobar">
     <div>
       <ol>
         <li>1</li>
         <li>2</li>
       </ol>
     </div>
     <div class="loginOrsignUp">
       <div class="circle">
         <i :class="iconStyle"></i>
       </div>
       <div @click="changeIcon">
         <el-button :plain="true" type="danger">注册</el-button>
         <el-button :plain="true" type="danger">登录</el-button>
       </div>

     </div>
  </div>
</template>

<script>
  export default {
    data() {
        return {
            iconStyle: 'el-icon-loading'
        }
    },
    methods: {
      changeIcon() {
         this.iconStyle = 'el-icon-check'
      }
    }
  }
</script>

<style scoped lang="scss">
  #toobar {
    min-height: 5em;
    padding-left: 140px;
    padding-right: 2em;
    background-color: #F1F1F1;
    display: flex;
    justify-content: space-between;
    align-items: center;
    >.loginOrsignUp{
      display: flex;
      align-items: center;
      >.circle{
        width: 2em;
        height: 2em;
        margin-right: 1em;
        border-radius: 50%;
        background-color: #AACD4F;
        display: flex;
        justify-content: center;
        align-items: center;
      }
    }
  }
</style>


