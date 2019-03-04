<template>
  <div id="app">
  	<vhead></vhead>
    <router-view/>
  </div>
</template>

<script>
import vhead from './components/common/Head'
export default {
  name: 'App',
  components: {
      // 可以以key-value的形式注册组件, 此时挂载点的名字就是key
      // 否则挂载点和组件名字一致, 即vhead
      vhead
    }
}
</script>

<style lang="less">

@import "./assets/css/common.less";
</style>
