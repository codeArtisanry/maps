<template>
  <div class="s1">
    <div v-for="country in countryInfo" :key="country" class="countries">
      <div class="country">
        <div class="country-img">
          <img :src="country.flags.png" alt="not found" />
        </div>
        <div class="countryinfo">
          <h5>
            <b>{{ country.name }}</b>
          </h5>
          <p><strong>Population:</strong>{{ country.population }}</p>
          <p><strong>Region:</strong>{{ country.region }}</p>
          <p><strong>Capital:</strong>{{ country.capital }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      countryInfo: [],
      url: 'https://restcountries.com/v2/all',
    }
  },
  async created() {
    const res = await this.$axios.$get(this.url)
    this.countryInfo = res
  },
}
</script>
