<template>
  <div class="navPosition">
    <div id="nav">
      <spam>{{ siteTitle }}</spam>
      <router-link to="/">Home</router-link
      ><router-link to="/about">About</router-link>
      <router-link to="/contact">Contact</router-link>
      <router-link to="/testimonial">Testimonial</router-link>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      siteTitle: "My Vue Application"
    };
  }
};
</script>
<style>
.navPosition {
  /* padding: 30px; */
  font-size: 1.3rem;
  background-color: lightgrey;
}
#nav {
  display: block;
  width: 60%;
  margin: 0 auto;
}
#nav a,
#nav spam {
  font-weight: bold;
  color: white;
  display: inline-block;
  padding: 30px 40px;
  border-left: 1px solid black;
}
#nav a:last-child {
  border-right: 1px solid black;
}
#nav a.router-link-exact-active {
  color: black;
  /* background-color: grey; */
}
#nav spam {
  font-size: 2rem;
  border: 0px;
  font-weight: bold;
  float: left;
}
</style>
