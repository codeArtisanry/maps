<template>
  <div>
    <TheHeader />
    <the-country-card :countries="countries" />
  </div>
</template>

<script>
import TheHeader from '~/components/TheHeader.vue'
export default {
  components: { TheHeader },
  data() {
    return {
      countries: [
        {
          name: '',
          nativeName: '',
          population: '',
          region: '',
          subregion: '',
          capital: '',
          languages: '',
          currencies: '',
          flags: {
            png: '',
          },
        },
      ],
      show_country: true,
    }
  },
  created() {
    this.fetchcountry()
  },
  methods: {
    async fetchcountry() {
      const res = await this.$axios.$get('https://restcountries.com/v2/all')
      this.countries = res
    },
  },
}
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
