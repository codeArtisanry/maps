<template>
  <div class="nav-item">
    <div class="container-fluid d-flex justify-content-between">
      <input
        class="search p-1 w-25 mx-4 mt-5 p-3 w-25"
        placeholder="Search for a country..."
        type="text"
      />
      <select
        id=""
        class="options mr-4 px-5 my-4 border-0 bg-white shadow w-30 font-font-weight-normal"
      >
        <option value="volvo">Filter By Region</option>
        <option value="Europe">Europe</option>
        <option value="Africa">Africa</option>
        <option value="Europe">Europe</option>
        <option value="Oceania">Oceania</option>
      </select>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {}
  },
}
</script>

<style>
.search {
  border-radius: 0.7em;
  width: 30em;
  border: none;
  box-shadow: rgb(100 100 111 / 20%) 0 7px 20px 0;
}
</style>
