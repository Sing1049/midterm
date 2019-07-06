<template>
  <div id="page">
    <h2 class="title">{{ pageTitle }}</h2>
    <div id="contact">
      <div>
        <h4>Address:</h4>
        <li>{{ Address.AddressLine1 }} {{ Address.AddressLine2 }}</li>
        <li>
          {{ Address.City }}, {{ Address.State }}-{{ Address.PostalCode }}
        </li>
        <h4>Phone Number:</h4>
        <li>{{ PhoneNumber }}</li>
      </div>
      <div>
        <h4>Working Hours</h4>
        <ul>
          <li v-for="time in WorkingHours">
            {{ time }}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      pageTitle: "Contact Us",
      Address: {
        AddressLine1: "1435",
        AddressLine2: "Woodroffe Avenue,",
        City: "Ottawa",
        State: "Ontario",
        PostalCode: "K2G 1V8"
      },
      PhoneNumber: "183939839839",
      WorkingHours: [
        "Monday :    8am-6pm",
        "Tuesday :   8am-6pm",
        "Wednesday : 8am-6pm",
        "Thursday :  8am-6pm",
        "Friday :    8am-5pm",
        "Saturday :  10am-4pm",
        "Sunday :    10am-2pm"
      ]
    };
  }
};
</script>
<style>
#page {
  width: 60%;
  margin: 0 auto;
}
#contact {
  font-size: 1.2rem;
  display: flex;
  width: 100%;
  margin: 0 auto;
}
#contact div {
  list-style-type: none;
  text-align: left;
  width: 50%;
  padding: 5px;
}
ul {
  list-style: none;
}
h4 {
  text-decoration: underline;
}
.title {
  font-size: 3rem;
  font-weight: bold;
}
</style>
