<template>
  <div class="nav-item">
    <div class="pl-4 pr-3 pr-5 d-flex pt-5 justify-content-between">
      <input
        class="search w-25 mx-4 mt-5 p-3 w-25"
        placeholder="        Search for a country..."
        type="text"
        required
      />
      <select
        id="select"
        class="mx-4 mt-5 p-2 w-20 border-0 bg-white shadow font-weight-bold"
      >
        <option value="">Filter By Region</option>
        <option value="Europe">Europe</option>
        <option value="Africa">Africa</option>
        <option value="Europe">Europe</option>
        <option value="Oceania">Oceania</option>
      </select>
    </div>
    <div class="row">
      <div
        v-for="(country, index) in countries"
        :key="index"
        class="col-lg-3 h-auto w-auto p-5 pl-5"
      >
        <router-link
          class="card font m-4 h-100 border-0 shadow-lg text-dark mb-2"
          :to="{ path: 'vatsal/' + country.name + '/countrydetails' }"
        >
          <div class="flag-img">
            <img
              class="card-img-top pt-2 flag-img"
              :src="country.flags.png"
              alt="..."
            />
          </div>
          <div class="card-body ml-lg-2">
            <h4 class="card-title font-weight-bold pb-2">{{ country.name }}</h4>
            <p class="card-text">
              Population:
              <span> {{ country.population }} <br /> </span>
              Region:
              <span> {{ country.region }} <br /> </span>
              Capital:
              <span> {{ country.capital }} <br /> </span>
            </p>
          </div>
        </router-link>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    countries: Array,
  },
  data() {
    return {}
  },
}
</script>
<style scoped>
.search {
  padding: 0.5% 6%;
  margin: 0.5%;
  background-image: url('https://www.pngarea.com/pngm/109/1164446_searchicon-png-search-icon-png-download.png');
  background-repeat: no-repeat;
  outline: 0;
  background-position: 12px;
  background-size: 16px;
  border-radius: 0.7em;
  width: 30em;
  border: none;
  box-shadow: rgb(100 100 111 / 20%) 0 7px 20px 0;
}

.flag-img {
  height: 220px;
  border-top-right-radius: 0.8rem;
  border-top-left-radius: 0.8rem;
}

p {
  font-weight: 600;
}

span {
  font-weight: 400;
}

.card {
  border-radius: 0.7rem;
}

.font {
  font-size: 1.2rem;
}
</style>
