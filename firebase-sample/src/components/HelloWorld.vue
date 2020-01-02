<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <button v-on:click="counter += 1">Add 1</button>
    <button v-on:click="reset">reset (use method)</button>
    <p>The button above has been clicked {{ counter }} times.</p>
    
    <button v-on:click="sample_request_Japan">request Japan</button>
    <button v-on:click="sample_request_Australia">request Australia</button>
  </div>
</template>

<script>
export default {
  // name: 'HelloWorld',
  data () {
    return {
      msg: 'hogehoge',
      counter: 0
    }
  },
  methods:{
    reset: function(event){
      this.counter = 0;
    },
    sample_request_Japan: function(event){
      this.msg = "Japan";
    },
    sample_request_Australia: function(event){
      this.msg = "Australia";
    }
  }
}
</script>

<style scoped>
h1, h2 {
  font-weight: normal;
}
</style>

