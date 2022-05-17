<template>

  <main class="wrapper">
    <h1>Products</h1>

    <div class="card-container">

      <ProductCard v-for="(product, index) in inventory"
                   :key="product.id"
                   :addToCart="addToCart"
                   :index="index"
                   :product="product"
      />
    </div>
  </main>
</template>

<script>
import ProductCard from "@/components/ProductCard.vue";

export default {
  components: {
    ProductCard
  },
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Products',

  props: ['inventory', 'addToCart']
}
</script>