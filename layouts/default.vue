<template>
  <div>
    <nav class="nav">
      <h1 class="logo">
        <NuxtLink to="/">
          Jewels <!-- Our Demo Website's Title -->
        </NuxtLink>
      </h1>
      <jamcart-open class="open" />
    </nav>

    <Nuxt />

    <footer class="demo">
      <p>
        Demo E-commerce website built with <a href="https://vuejs.org/">Vue.js</a>, <a href="https://nuxtjs.org/">Nuxt.js</a>, and <a href="https://jamcart.io">JamCart</a>
      </p>
      <p>
        Source available on <a href="https://github.com/JamCart/vue-nuxt-demo">GitHub</a>
      </p>
      <p>
        Photos by <a href="https://unsplash.com/@sabrinnaringquist?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Sabrinna Ringquist</a> on <a href="https://unsplash.com/@sabrinnaringquist?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
      </p>
    </footer>
  </div>
</template>

<style scoped>
@font-face {
  font-family: 'Cinzel';
  font-style: normal;
  font-weight: 500;
  src: url(~assets/Cinzel-SemiBold.woff2) format('woff2');
}

.demo {
  color: #666;
  margin: 3em 0;
  text-align: center;
}
.demo a {
  color: #222;
  text-decoration: underline;
}
.demo p {
  margin: .5em 0;
}

.nav {
  align-items: center;
  display: grid;
  grid-template: "logo cart" "categories categories";
  margin: 2em 0;
}
@media (min-width: 45em) {
  .demo {
    text-align: right;
  }
  .demo p {
    margin: 0;
  }
  .nav {
    grid-template: "logo categories cart" / min-content 1fr min-content;
  }
}

.logo {
  font-family: Cinzel;
  font-size: 250%;
  font-weight: 500;
  grid-area: logo;
  grid-gap: 1em;
  margin: 0 1em 0 0;
}

.open {
  grid-area: cart;
  margin-left: auto;
}
</style>
