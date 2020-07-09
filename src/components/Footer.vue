<template>
  <footer>
    <section class="container row">
      <p>{{copyright}}</p>
      <div class="follow">
        <a
          href="https://github.com/terieyenike"
          target="_blank"
          rel="noopener noreferrer"
          class="link"
        >
          <i class="fab fa-github"></i>
        </a>

        <a
          href="https://linkedin.com/in/terieyenike"
          target="_blank"
          rel="noopener noreferrer"
          class="link"
        >
          <i class="fab fa-linkedin"></i>
        </a>

        <a
          href="https://twitter.com/terieyenike"
          target="_blank"
          rel="noopener noreferrer"
          class="link"
        >
          <i class="fab fa-twitter"></i>
        </a>
      </div>
    </section>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      copyright: "Teri © 2020. all rights reserved"
    };
  }
};
</script>

<style scoped>
footer {
  text-align: center;
  padding: 1em 0;

  color: rgb(221, 221, 221);
  background: black;
}

footer p {
  font-size: 1.1rem;
}

.follow {
  display: flex;
  margin-top: 0.85em;
  justify-content: space-around;
}

footer a {
  color: rgb(221, 221, 221);
}

@media screen and (min-width: 768px) {
  .follow {
    margin: 0;
  }

  .link + .link {
    margin: 0 0 0 1.5em;
  }

  .fab {
    font-size: 1.5rem;
  }

  .row {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  a:nth-of-type(2):hover {
    color: #0277b5;
  }

  a:nth-of-type(3):hover {
    color: #38a1f3;
  }
}
</style>