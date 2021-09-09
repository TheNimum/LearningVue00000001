<template>
  <div class="hello">
    
     <!-- en räknare som plus, minus och reset knapp  -->
    <div class="btn-counter">
      <h1> Click Counter </h1>
    <h2> {{ i }} </h2>
    <button class="btn increase"
     v-show="showButton"
     v-on:click="increase">
     + </button>
    <button class="btn decrease"
     v-show="showButton"
     v-on:click="decrease">
     - </button>
    <button class="btn reset" 
    v-show="resetCountButton" 
    v-on:click="resetButton">
      Reset button</button>
    </div>
    
    
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
    showButton: true,
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
.btn-counter{
  
  background-color: rgb(168, 226, 226);
  border:indigo;
  border: dotted hotpink;
  text-align: center;
  padding-bottom: 2em;
  padding-top: 1em;
  
  text-align: center;
  border-radius: 1em;
  
  
  
}


.btn{  
  font-size: 1em;
  background-color: rgb(255, 255, 4);
  padding:0.5em;
  margin:0.1em;
  border: groove rgb(33, 3, 71);
  border-radius: 10px;
}
.btn:hover{ background-color: greenyellow;}


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
