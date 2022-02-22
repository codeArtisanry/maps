<template>
  <div>
    <the-header />
    <div class="pl-4">
      <button class="btn backbtn" @click="Back">
        <img
          class="back"
          :src="require('@/static/arrow-back-outline.svg')"
          alt="back button"
        />
        Back
      </button>
      <div class="card border-0 p-2">
        <div class="row">
          <div class="col-md-6">
            <div class="card-img pl-5 flag">
              <img class="flag" :src="countries[0].flag" alt="country flag" />
            </div>
          </div>
          <div class="col-md-6 pt-5">
            <h2 class="title">{{ countries[0].name }}</h2>
            <div class="row">
              <div class="col-md-6">
                <p>
                  Native Name:
                  <span class="spa">{{ countries[0].nativeName }}</span>
                </p>
                <p>
                  Population:
                  <span class="spa">{{ countries[0].population }}</span>
                </p>
                <p>
                  Region:
                  <span class="spa">{{ countries[0].region }}</span>
                </p>
                <p>
                  Sub Region:
                  <span class="spa">{{ countries[0].subregion }}</span>
                </p>
                <p>
                  Capital:
                  <span class="spa">{{ countries[0].capital }}</span>
                </p>
                <p>
                  Top Level Domain:
                  <span class="spa">{{ countries[0].topLevelDomain[0] }}</span>
                </p>
                <p>
                  Currencies:
                  <span class="spa">{{
                    countries[0].currencies[0].symbol
                  }}</span>
                  <span class="spa">{{ countries[0].currencies[0].name }}</span>
                </p>
                <p>
                  Languages:
                  <span class="spa">{{ countries[0].languages[0].name }}</span>
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
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
          topLevelDomain: '',
          currencies: [{ name: '' }],
          languages: [{ name: '' }],
          flags: { png: '' },
        },
      ],
    }
  },
  created() {
    this.fetchcountry()
  },
  methods: {
    async fetchcountry() {
      const res = await this.$axios.$get(
        'https://restcountries.com/v2/name/' + this.$route.params.id
      )
      this.countries = res
    },
    // async getCountriesByCode(countryName) {
    //   const res = await this.$axios.$get(
    //     'https://restcountries.com/v2/all/' + index
    //   )
    //   this.index.name = res[0].name
    //   this.$router.push('/vatsal/' + this.countrydetails.id + '/countrydetails')
    // },
    Back() {
      this.$router.push('/vatsal')
    },
  },
}
</script>

<style>
.card {
  font-size: 1.1em;
}

.spa {
  text-decoration: none;
  font-weight: 400;
}

.title {
  font-size: 4em;
  font-weight: 600;
}

.flag {
  display: flex;
  margin-top: 2em;
  max-width: 34em;
}

.backbtn {
  margin-top: 5em;
  background-color: white;
  border: none;
  color: black;
  box-shadow: rgb(99 99 99 / 20%) 0 2px 8px 0;
  margin-left: 3.5em;
  padding-inline: 3em;
}
</style>
