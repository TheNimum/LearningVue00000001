<template>
  <div class="hello">
    <h1> Vue demo !  </h1>
    <p>{{ exempel }}</p>
    <button v-show="showButton" v-on:click="increase"> increase by 1 = {{i}}</button>
    <button v-show="!showButton" v-on:click="decrease"> decrease by 1 = {{i}}</button>
    <button v-show="testButton" v-on:click="doShowText"> show hidden text</button>
    <p> {{doShowText ? testButton: ""}} </p>
  </div>
</template>

<script>

export default {
  name: 'HelloWorld',
  
  data: () => ({
    exempel: 'detta är ett exempel på en data property.',
    showButton: true,
    testButton: 'this is illuminated',
    doshowText: true,
    i: 0, 
  }),
  methods: { 

    doShowText() {
      this.showText = false

    },
    
    increase() { 
      console.log('Inside increase');
    this.i++
    if(this.i === 10)
    {
      this.showButton = !this.doShowText
    }
    },

    decrease() { console.log('Inside decrease');
    this.i--
    if(this.i === 0) // fixa denna så att den byter tillbaka till andra knappen .. .. .  
    {
      this.showButton = !this.showButton
    }
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
