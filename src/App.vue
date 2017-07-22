<template>
  <div id="app">
    <Toobar class="toobar"/>
    <main>
      <Editor class="editor"/>
      <Preview class="preview"/>
    </main>
  </div>
</template>

<script>
import Toobar from './components/Toobar'
import Editor from './components/Editor'
import Preview from './components/Preview'

export default {
  name: 'app',
  components: {
    Toobar,
    Preview,
    Editor
  }
}
</script>

<style lang="scss">
  body{
    background: #252A30;
    padding: 2em;
  }
  html,body, main{
    height: 100%;
    overflow: hidden;
  }
  #app{
    height: calc(100% - 4em);
    background-color: #FFFFFF;
  }
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    position: relative;
    display: flex;
    flex-direction: column;
    box-shadow: 0 0 3px 1px #21262A,0 0 3px 1px #21262A,0 0 3px 1px #21262A;
  }
  main {
    display: flex;
    flex: 1;
    > .editor {
      width: 30em !important;
    }
    > .preview {
      flex: 1;
      overflow-y:scroll;
    }
  }
</style>
