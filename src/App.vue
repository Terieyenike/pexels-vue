<template>
  <div>
    <Home />
  </div>
</template>

<script>
import Home from "../homeDup";
export default {
  name: "app",
  components: {
    Home
  }
};
</script>

<style lang='css'>
@import url("https://fonts.googleapis.com/css?family=Fira+Sans|Montserrat&display=swap");

body {
  font-size: 1.3rem;
  font-family: "Fira Sans", sans-serif;
}

.container {
  margin: 0 auto;
  max-width: 1200px;
  width: 85%;
}

a {
  text-decoration: none;
  color: #333;
}
</style>
