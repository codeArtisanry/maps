<template>
  <div class="text-center">
    <div class="row">
      <div
        v-for="country in countries"
        :key="country"
        class="col-lg-3 h-auto w-auto p-5"
      >
        <div class="card m-5 h-100">
          <img
            class="card-img-top p-4 pt-5 w"
            :src="country.flags.png"
            alt="..."
          />
          <div class="card-body">
            <h5 class="card-title">{{ country.name }}</h5>
            <p class="card-text">
              Population:
              {{ country.population }} <br />

              Region:
              {{ country.region }} <br />

              Capital:
              {{ country.capital }} <br />
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      country: {},
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
  mounted() {
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
