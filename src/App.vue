<template>
  <div id="app">
    <img src="./assets/logo.png">
    <div>
      <group>
        <cell title="vux包装的weui组件cell" value="cool"></cell>
      </group>
    </div>
    <hello></hello>
  </div>
</template>

<script>
import Hello from './components/Hello'
import XButton from 'vux/src/components/x-button'
import Group from 'vux/src/components/group'
import Cell from 'vux/src/components/cell'

export default {
  name: 'app',
  components: {
    Hello,
    XButton,
    Group,
    Cell
  }
}
</script>

<style>
@import '~vux/dist/vux.css';
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
