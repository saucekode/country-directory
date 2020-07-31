<template>
  <div id="app" class="app d-flex dc-flex j-btw" :class="mode">
      <Header 
        :mode="mode" 
        :modeIcon="modeIcon" 
        :modeText="modeText" 
        @toggle="toggle"
      />

      <Content :mode="mode"/>
  </div>
</template>

<script>
import Header from './components/Shared/Header';
import Content from './components/Page/Content'

export default {
  name: 'App',
  data(){
    return {
      mode: 'light',
      modeText: 'dark',
      modeIcon: 'fa fa-moon-o'
    }
  },
  components:{
    Header,
    Content
  },
  methods: {
    toggle(){
      if(this.mode == 'light'){
        this.mode = "dark";
        this.modeText = "light";
        this.modeIcon = "fa fa-sun-o"
      }else{
        this.mode = "light";
        this.modeText = "dark";
        this.modeIcon = "fa fa-moon-o"
      }
    }
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Nunito+Sans:wght@300;600;800&display=swap');

  body, *, *::after, *::before{
    padding: 0;
    margin: 0;
    outline: none;
    border: none;
    font-family: 'Nunito sans'

  }

  .app{
    min-height: 100vh;
    font-family: 'Nunito Sans', sans-serif;
  }

  .cursor-pointer{
    cursor: pointer;
  }

  button{
    background: transparent;
    border: none;
    outline: none;
  }

  button:hover, button:focus{
    border: none;
    outline: none;
  }

  .d-flex{
    display: flex;
  }

  .j-btw{
    justify-content: space-between;
  }

  .dc-flex{
    display: flex;
    flex-direction: column;
  }

  .align-items{
    align-items: center;
  }

  .cursor-point{
    cursor: pointer;
  }

  .dark{
    color: #fff;
  }

</style>