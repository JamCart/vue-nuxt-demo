<template>
  <main>
    <ul class="product-grid">
      <li v-for="(product, index) in products" :key="product.slug">
        <NuxtLink :to="`/product/${ product.slug }`">
          <a class="product">
            <div class="product-image">
              <img alt="" height="427" width="640" :src="product.image" :loading="index < 3 ? 'eager' : 'lazy'" />
            </div>
            <div class="product-description">
              {{ product.name }}
            </div>
            <div class="product-price">
              {{ product.price }}
            </div>
          </a>
        </NuxtLink>
      </li>
    </ul>
  </main>
</template>

<script>
export default {
  async asyncData ({ $content }) {
    const products = await $content('product').fetch()
    return { products }
  }
}
</script>

<style scoped>
.product-grid {
  display: grid;
  font-weight: 500;
  grid-gap: 4em 1.5em;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  list-style: none;
  margin: 0;
  padding: 0;
}

.product {
  display: grid;
  grid-gap: .5rem 1rem;
  grid-template: 'img img' 'desc price' / 1fr min-content;
  line-height: 1.5rem;
}
.product-description {
  font-size: 110%;
}
.product-price {
  color: #525252;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}
.product-description,
.product-price {
  padding: 0 6px;
}

.product-image {
  border: 3px solid #d4d7de;
  border-radius: 5px;
  grid-area: img;
  overflow: hidden;
}
.product-image * {
  vertical-align: middle;
}

.product-image img {
  height: auto;
  transition: transform .2s ease-out;
  width: 100%;
}
.product:hover .product-image img {
  transform: scale(1.3);
  transform-origin: center;
}
</style>
