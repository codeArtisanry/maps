<template>
  <div>
    <b-navbar class="nav-bar">
      <b-navbar-item class="ml-4 nav-heading">
        Where in the world ?
      </b-navbar-item>
      <b-navbar-nav class="ml-auto">
        <b-nav-item class="mr-4">
          <img
            class="moon"
            :src="require('@/static/moon-outline.svg')"
            alt="moon"
          />
          <button class="darkmode">Dark Mode</button>
        </b-nav-item>
      </b-navbar-nav>
    </b-navbar>
  </div>
</template>
<script>
export default {}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Nunito+Sans:wght@300;600;800&display=swap');

.nav-bar {
  background-color: white;
  box-shadow: rgb(100 100 111 / 20%) 0 7px 29px 0;
}

.darkmode {
  border-style: none;
  color: #2b3743;
  background-color:white;
  font-weight: 600;
  font-family: 'Nunito Sans', sans-serif;
}

.nav-heading {
  color:#2b3743;
  font-weight: 800;
  font-family: 'Nunito Sans', sans-serif;
  font-size: 17px;
}

.moon {
  height: 25px;
}

@media (max-width: 398px){
.nav-heading{
  font-weight: 600;
  font-size: 10px;
}

.moon{
  margin-top: 2%;
  height: 10px;
}

.darkmode{
font-size:10px;
}
}
</style>
