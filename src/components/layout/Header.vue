<template>
  <header>
      <h1 class="heading">{{heading}}</h1>
  </header>
</template>

<script>
export default {
    props:{
        heading: String
    }

}
</script>

<style scoped>
.heading{
    background: #000;
    color: #fff;
    text-align: center;
    padding: 10px;
}
</style>