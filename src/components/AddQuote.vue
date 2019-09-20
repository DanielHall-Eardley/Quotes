<template lang="html">
  <div class="add-quote">
    <h3>Quote</h3>
    <textarea v-model="input"></textarea>
    <button @click="submitQuote()">Add Quote</button>
  </div>
</template>

<script>
export default {
  data(){
    return{
      input: ""
    }
  },
  methods:{
    submitQuote(){
      this.$emit("addQuote", this.input)
      this.input = ""
    }
  }
}
</script>

<style lang="css">
  .add-quote{
   width: 80%;
   margin: 0 auto;
  }

  .add-quote > textarea{
    display: block;
    height: 10rem;
    width: 100%;
    font-size: 2rem;
  }

  .add-quote > button{
    display: block;
    margin: 1rem auto;
    background-color: blue;
    border-radius: 4px;
    color: white;
    font-size: 1.8rem;
    border: none;
    padding: .5rem 1rem;
  }
</style>
