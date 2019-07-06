<template>
  <div id="nav">
    <spam>Vue Application</spam>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link to="/contact">Contact</router-link> |
    <router-link to="/testimonial">Testimonial</router-link>
  </div>
</template>
<style>
#nav {
  padding: 30px;
  font-size: 1.3rem;
  background-color: lightgrey;
}

#nav a {
  font-weight: bold;
  color: white;
}

#nav a.router-link-exact-active {
  color: black;
  background-color: grey;
}
#nav spam {
  font-size: 1.3rem;
  font-weight: bold;
  float: left;
  /* padding-left: 30px; */
}
</style>
