<template>
  <div class="hello">
    
     
    
    
    
      <!-- här vill jag göra en knapp som gör saker onsynlig eller synlig -->
    <div class="HideAndShow">
      <h1>Hide and Show Button</h1>
      <h2> Show the Hidden text: <span class="hiddenText" v-show="visible"> {{secretText}}</span> </h2>
      <button class="showAndHide" 
      v-show="nowYouSee" 
      v-on:click="revealButton"> {{buttontext}}</button>
    </div>
    

  </div>
</template>

<script>

export default {
  name: 'HelloWorld',
  
  data: () => ({
    
    ShowText: true,
    resetCountButton: true,
    nowYouSee: true,
    visible: true,
    secretText: 'You found me!',

    i: 0, 
  }),
  computed: {
    buttontext(){
      if (this.visible) {
        return 'hide text'
        
      }else
      return 'show text'
    }
  },
  

  methods: { 
    revealButton(){ 
      this.visible = !this.visible;
    },
    resetButton() {
      this.i = 0;
    }, 
    increase() { 
    this.i++
    },
    decrease() { 
    this.i--  
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.HideAndShow{
  font-size: 15px;
  border: maroon;
  padding: 0.5em;
  margin: 1em;
  border:dotted black;
  background: crimson;
  
}



h3 {
  margin: 40px;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
