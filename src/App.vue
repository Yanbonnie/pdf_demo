<template>
  <div id="app">
    <dragModel>
      <ul class="sign_page_scroll" slot="dragTop">
          <li>元旦快乐</li>
          <li>元旦快乐</li>
          <li>元旦快乐</li>
          <li>元旦快乐</li>
          <li>元旦快乐</li>
          <li>元旦快乐</li>
          <li>元旦快乐</li>
          <li>元旦快乐</li>
          <li>元旦快乐</li>
          <li>元旦快乐</li>
          <li>元旦快乐</li>
          <li>元旦快乐</li>
          <li>元旦快乐</li>
          <li>元旦快乐</li>
          <li>元旦快乐</li>
          <li>元旦快乐</li>
          <li>元旦快乐</li>
          <li>元旦快乐</li>
        </ul>
        <div slot="dragBottom">
          <h3>元旦快乐</h3>
        </div>
    </dragModel>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
*{
  padding: 0;
  margin: 0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
