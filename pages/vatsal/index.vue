<template>
  <div>
    <TheHeader />
    <the-search />
  </div>
</template>

<script>
import TheHeader from '~/components/TheHeader.vue'
import TheSearch from '~/components/TheSearch.vue'
export default { components: { TheHeader, TheSearch } }
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Karla:wght@500&family=Rubik:wght@400;500;700&display=swap');

* {
  box-sizing: border-box;
  font-family: 'Nunito Sans', sans-serif;
  font-weight: 700;
  margin: 0;
  padding: 0;
}
</style>
