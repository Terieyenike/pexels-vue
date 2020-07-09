<template>
  <div>
    <section class="header">
      <div class="search">
        <input
          type="text"
          name="query"
          v-model="query"
          class="input"
          :placeholder="search"
          @keyup.enter="searchPhotos"
        />
      </div>
      <p class="credit">
        Photos provided by
        <a
          href="https://www.pexels.com/"
          target="_blank"
          rel="noopener noreferrer"
        >Pexels</a>
      </p>
    </section>

    <image-grid :photos="photos" />

    <Footer />
  </div>
</template>

<script>
import ImageGrid from "./ImageGrid";
import Footer from "./Footer";
export default {
  name: "app-home",

  components: {
    ImageGrid,
    Footer
  },
  data() {
    return {
      search: "Search for free photos",
      query: "cave",
      apiKey: "YOUR_API_KEY",
      apiUrl: "https://api.pexels.com/v1/search/",
      photos: null
    };
  },
  methods: {
    searchPhotos() {
      const url = `${this.apiUrl}?query=${this.query}`;
      const getPexels = url => {
        const options = {
          method: "GET",
          headers: {
            Authorization: this.apiKey
          }
        };
        const result = fetch(url, options)
          .then(res => res.json())
          //eslint-disable-next-line
          .then(data => {
            this.photos = data.photos;
          });

        return result;
      };
      getPexels(url);
      this.query = "";
    }
  },
  created() {
    this.searchPhotos();
  }
};
</script>

<style scoped>
.header {
  background: rgb(243, 243, 243);
  padding: 2em 0;
  position: relative;
}

.credit {
  position: absolute;
  bottom: 0;
  right: 0;
  font-size: 0.75rem;
  font-family: Montserrat, sans-serif;
  padding: 0 1em 0;
}

.credit a:hover,
.credit a:active {
  color: #51b9a2;
  font-weight: 700;
}

input[type="text"] {
  width: 100%;
  padding: 1em;
  border-radius: 0.5em;
  border: 0;
  outline: none;
}

.search {
  text-align: center;
}

.search .input {
  width: 85%;
  text-indent: 1.875rem;
  color: #333;
  font-size: 1rem;
}

@media screen and (min-width: 768px) {
  .credit {
    font-size: 1rem;
  }

  .search {
    margin-bottom: 0.85em;
  }
}

@media screen and (min-width: 1500px) {
  .search .input {
    width: 50%;
  }
}
</style>