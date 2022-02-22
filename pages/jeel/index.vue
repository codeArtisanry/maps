<template>
  <div>
    <Navbar />
    <Country-Card :countries-data="countriesData" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      countriesData: [
        {
          name: '',
          flags: {
            png: '',
          },
          population: '',
          region: '',
          capital: '',
        },
      ],
    }
  },
  created() {
    this.getCountriesData()
  },
  methods: {
    async getCountriesData() {
      const res = await this.$axios.$get('https://restcountries.com/v2/all')
      this.countriesData = res
    },
  },
}
</script>
