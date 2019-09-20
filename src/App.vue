<template>
  <div class="container">
    <Header :quotes="quoteArray"></Header>
    <AddQuote v-on:addQuote="updateQuoteList"></AddQuote>
    <QuoteList :quotes="quoteArray" v-on:deleteQuote="deleteQuote">
    </QuoteList>
    <Footer></Footer>
  </div>
</template>

<script>
  import Header from "./components/Header.vue"
  import AddQuote from "./components/AddQuote.vue"
  import QuoteList from "./components/QuoteList.vue"
  import Footer from "./components/Footer.vue"

  export default {
    data(){
      return{
        quoteArray: [
          "It's a good day to die hard"
        ]
      }
    },
    components:{
      Header,
      AddQuote,
      Footer,
      QuoteList
    },
    methods:{
      updateQuoteList(data){
        if(this.quoteArray.length  < 10){
          this.quoteArray.push(data)
          document.querySelector(".header-progress").style.width = this.quoteArray.length + "0%"
        }else{
          alert("maximum quote quota reached")
        }
      },
      deleteQuote(e){
        this.quoteArray = this.quoteArray.filter(el => {
          if(e.srcElement.innerText !== el){
            return el
          }
        })

        document.querySelector(".header-progress").style.width = this.quoteArray.length + "0%"
      }
    }
  }
</script>

<style>
</style>
