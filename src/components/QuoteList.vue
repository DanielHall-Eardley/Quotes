<template lang="html">
  <section class="list">
    <div class="list-item"
      v-for="quote in quotes"
      @click="deleteQuote($event)">
      {{quote}}
    </div>
  </section>
</template>

<script>
  export default {
    props: ["quotes"],
    methods: {
      deleteQuote(e){
        this.$emit("deleteQuote", e)
      }
    }
  }
</script>

<style lang="css">
  .list{
    width: 100%;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(min-content, 23%));
    grid-gap: 1rem;
    justify-content: center;
  }

  .list-item{
    flex: 0 25%;
    padding: 3rem 1rem;
    border: solid .4px lightgrey;
    font-family: "Arizonia" cursive;
  }

  .list-item:hover{
    background-color: lightpink
  }
</style>
