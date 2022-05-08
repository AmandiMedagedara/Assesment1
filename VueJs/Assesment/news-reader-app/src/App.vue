<template>
  <div id="app">
    <News :apiKey="apiKey" />
    <!-- <SourceSelection :apiKey="apiKey"/> -->
  </div>
</template>

<script>
import News from "./components/News.vue";
import SourceSelection from "./components/SourceSelection.vue";

export default {
  name: 'app',
   data: () => {
     return {
       apiKey: 'e854a736aa0c48298c16f4ad51df3024' //Get api key from newsapi.org
     }
   },
  components: {
    // SourceSelection,
    News,
}
}
</script>

<style lang="scss">
 @import url('https://use.fontawesome.com/releases/v5.7.2/css/all.css');

body {
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100vw;
    height: 100vh;
    font-family: 'NTR', sans-serif;
    background: #eee;
}

#app {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 1rem;
  color: #333;
  height: 100%;
  background-color: #fff;
  border: 2px solid #222;
  border-radius: 20px;
  box-shadow: 5px 10px 18px #222;
  overflow-y: scroll;
  overflow-x: hidden;
} 
  ::-webkit-scrollbar {
    display: none;
  }
</style>

