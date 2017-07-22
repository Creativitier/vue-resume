<template>
  <div id="editor">
    <nav class="nav">
      <header class="imgHead">
        <svg class="icon icon-zhuangshitubiao06" aria-hidden="true" style="fill: #D81F1F">
          <use xlink:href="#icon-zhuangshitubiao06"></use>
        </svg>
      </header>
      <p>...</p>
      <ol class="navbar">
        <li v-for="(value, index) in icons" @click="currentTab=index" :class="{active:currentTab===index}">
          <svg class="icon" aria-hidden="true">
            <use v-bind:xlink:href="`#icon-${icons[index]}`"></use>
          </svg>
          <span>{{ info[index] }}</span>
        </li>
      </ol>
    </nav>
    <ol class="resume-info">
      <li v-for="(value, index) in icons" v-if="currentTab===index">{{ value }}</li>
    </ol>
  </div>
</template>

<script>
  export default {
      data() {
          return {
            icons: [ 'gerenxinxi1','shiliangzhinengduixiang1','jiangli', 'project',  'book', 'dianhua'],
            info: ['个人', '项目', '学校', '公司', '奖励', '电话'],
            currentTab: 0,

          }
      }
   }
</script>

<style scoped lang="scss">
  .active{
    background-color: #fff;
  }

  .icon {
    width: 1em; height: 1em;
    vertical-align: -0.15em;
    fill: #4D5154;
    overflow: hidden;
    font-size: 2em;
  }
  #editor{
    width: inherit;
    min-height: 100px;
    display: flex;
  }
  .nav{
     display: flex;
     flex-direction: column;
     align-items: center;
     position: absolute;
     width: inherit;
     height: 100%;
     top: 0;
     background-color: #292E34;
     width: 7em;
     color: #fff;
     perspective: 1200px;
     overflow: hidden;
    > .imgHead {
       width: 5em;
       height: 5em;
       background-image: url(../assets/head.png);
       background-position: 50% 50%;
       border-radius: 50%;
       margin-bottom: 1.25em;
       position: relative;
       margin: 1.25em auto 0;
       border: 1px solid #838383;
       box-shadow: 0 0 3px 0 #838383;
       transition: all ease 1s;
       > .icon-zhuangshitubiao06 {
         position: absolute;
         right: -0.2em;
       }
       &:hover{
         transform: translate3d(0,0, 1em);
         opacity: 0.5;
       }
     }
     > p {
      font-size: 1.4em;
      color: #555658;
     } 
     > .navbar {
       margin-top: 2em;
       width: inherit;
       > li {
         width: inherit;
         text-align: center;
         padding: 1em 0;
         transition: all linear 0.5s;
         color: #4D5154;
         position: relative;
         overflow: hidden;
         > span{
           display: block;
           color: #4D5154;
           font-size: 0.6em;
         }
       }
     }
  }
  .resume-info{
    width: inherit;
    border: 1px solid red;
    margin: 1.25em;
    margin-left: 7em;
    > li {
      width: 100%;
      height: 100%;
    }
  }
</style>
