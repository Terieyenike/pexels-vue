<template>
  <section class="img-section">
    <!-- <div v-if="loading" class="container">Loading…</div> -->
    <div class="container card">
      <div class="card-box" v-for="photo in photos" :key="photo.id">
        <img :src="photo.src.large" alt="photographers photos" class="img" />
        <div class="card--info">
          <p>
            <a
              :href="photo.photographer_url"
              target="_blank"
              rel="noopener noreferrer"
            >{{photo.photographer}}</a>
          </p>
        </div>
        <div class="overlay"></div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "image-grid",
  // data() {
  //   return {
  //     loading: true
  //   };
  // },
  props: {
    photos: Array
  }
};
</script>

<style scoped>
.img-section {
  padding: 2.5em 0;
}

.img {
  box-shadow: 0 5px 15px 2px rgba(0, 0, 0, 0.2);
}

.card--info p {
  font-size: 1rem;
  /* margin-bottom: 1.5em; */
  cursor: pointer;
  font-family: Montserrat, sans-serif;
}

.card {
  grid-auto-flow: dense;
}

.card-box {
  margin-bottom: 0.625em;
}

@media screen and (min-width: 768px) {
  .card {
    display: grid;
    gap: 2em;
    grid-template-columns: repeat(2, 1fr);
  }

  .card--info p {
    margin-top: 1em;
  }
}

@media screen and (min-width: 1025px) {
  .card {
    grid-template-columns: repeat(3, 1fr);
  }
}

@media screen and (min-width: 1500px) {
  .card {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>