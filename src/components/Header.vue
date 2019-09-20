<template lang="html">
  <div class="header">
    <h1>Quotes Added</h1>
    <div class="header-background-box">
      <div class="header-progress">
        {{quotes.length}} / 10
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props: ["quotes"],
  }
</script>

<style lang="css">

  .header-background-box{
    height: 4rem;
    width: 100%;
    background-color: lightgrey;
    border-radius: 4px;
  }

  .header-progress{
    height: 100%;
    width: 10%;
    border-radius: 4px;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: blue;
    color: white;
    font-size: 1.8rem;
    transition: all .3s;
  }

</style>
