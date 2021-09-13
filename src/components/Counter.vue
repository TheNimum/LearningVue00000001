<template>
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
</template>

<script>


export default ({
	data: () => ({
		resetCountButton: true,
		showButton: true,
		i: 0,
	}),
	methods: {
	
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
	
})
</script>

<style scoped>
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
  padding:1em;
  margin:0.6em;
  border: groove rgb(33, 3, 71);
  border-radius: 10px;
}
.btn:hover{ background-color: greenyellow;}
</style>
