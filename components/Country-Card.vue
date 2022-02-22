<template>
  <div class="country-list">
    <div class="d-flex justify-content-between row">
      <div class="col-lg-6 search-box">
        <input
          id="search-bar"
          v-model="search"
          type="text"
          placeholder="Search for a Country..."
          class="mt-5"
          required
        />
      </div>
      <div class="col-lg-6 select-box">
        <select id="selected" v-model="selected" name="category" class="mt-5">
          <option value="">Filter by Regions</option>
          <option value="Asia">Asia</option>
          <option value="Europe">Europe</option>
          <option value="Africa">Africa</option>
          <option value="Europe">Europe</option>
          <option value="Oceania">Oceania</option>
        </select>
      </div>
    </div>
    <div
      v-for="country in filterCountry"
      :key="country.name"
      class="card col-lg-3"
      style="width: 13rem"
    >
      <router-link
        class="card-block stretched-link text-decoration-none"
        :to="{ path: 'jeel/' + country.name + '/Details' }"
      >
        <div class="flag-img">
          <img :src="country.flags.png" class="card-img-top" alt="..." />
        </div>

        <div class="card-body">
          <h1 class="py-3">{{ country.name }}</h1>
          <h3 class="d-inline">Population: :</h3>
          <p class="d-inline">{{ country.population }}</p>
          <br />
          <h3 class="d-inline">Region: :</h3>
          <p class="d-inline">{{ country.region }}</p>
          <br />
          <h3 class="d-inline">Capital:</h3>
          <p class="d-inline">{{ country.capital }}</p>
        </div>
      </router-link>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    countriesData: Array,
  },
  data() {
    return {
      search: '',
      selected: '',
    }
  },
  computed: {
    filterCountry() {
      return this.countriesData
        .filter((country) => {
          return country.name.match(this.search)
        })
        .filter((country) => {
          return country.region.match(this.selected)
        })
    },
  },
}
</script>
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Nunito+Sans:wght@300;600;800&display=swap');

input {
  width: 50%;
  border-radius: 5px;
  border: 1px solid #ada9a9;
  padding: 1% 6%;
  margin: 0.5%;
  background-image: url('~/static/search-outline.svg');
  background-repeat: no-repeat;
  outline: 0;
  background-position: 12px;
  background-size: 16px;
  border-style: none;
  box-shadow: rgb(100 100 111 / 20%) 0 7px 29px 0;
  margin-left: 27%;
}

#selected {
  margin-right: 27%;
  font-weight: 600;
  font-family: 'Nunito Sans', sans-serif;
  color: gray;
  padding: 1% 2%;
  box-shadow: rgb(100 100 111 / 20%) 0 7px 29px 0;
  border-style: none;
  border-radius: 5px;
  background-color: white;
  outline: none;
}

.search-box {
  text-align: left;
}

option {
  border-style: none;
  font-weight: 600;
  font-family: 'Nunito Sans', sans-serif;
  color: gray;
  font-size: 12px;
}

.select-box {
  text-align: right;
}

.card {
  text-align: left;
  display: inline-block;
  box-shadow: rgb(100 100 111 / 20%) 0 7px 29px 0;
}

.card:hover {
  background-color: lightgray;
}

.flag-img {
  padding-top: 10%;
  height: 115px;
  width: 170px;
}

h1 {
  font-size: 15px;
  color: black;
}

h3 {
  font-size: 12px;
  color: black;
}

p {
  font-size: 12px;
  color: black;
}

.col-lg-3 {
  margin: 5%;
}

.country-list {
  text-align: center;
}

@media (max-width: 991px) {
  #search-bar {
    margin: 0;
  }

  #selected {
    margin: 0;
  }

  .select-box {
    text-align: center;
  }

  .search-box {
    text-align: center;
  }
}
</style>
