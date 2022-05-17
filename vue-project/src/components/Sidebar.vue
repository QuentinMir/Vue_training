<template>
  <aside class="cart-container">
    <div class="cart">
      <h1 class="cart-title spread">
            <span>
              Cart
              <i class="icofont-cart-alt icofont-1x"></i>
            </span>
        <button @click="toggle" class="cart-close">&times;</button>
      </h1>

      <div class="cart-body">
        <table class="cart-table">
          <thead>
          <tr>
            <th><span class="sr-only">Product Image</span></th>
            <th>Product</th>
            <th>Price</th>
            <th>Qty</th>
            <th>Total</th>
            <th><span class="sr-only">Actions</span></th>
          </tr>
          </thead>
          <tbody>
          <tr v-for="(qty, key, i) in cart" :key="i">
            <td><i class="icofont-carrot icofont-3x"></i></td>
            <td>{{ key }}</td>
            <td>$ {{ getPrice(key) }}</td>
            <td class="center">{{ qty }}</td>
            <td>$ {{ (getPrice(key) * qty).toFixed(2) }}</td>
            <td class="center">
              <button @click="removeItem(key)" class="btn btn-light cart-remove">
                &times;
              </button>
            </td>
          </tr>


          </tbody>
        </table>

        <p v-if="Object.keys(cart).length === 0" class="center"><em>No items in cart</em></p>
        <div class="spread">
          <span><strong>Total:</strong> $ {{ cartTotal() }}</span>
          <button class="btn btn-light">Checkout</button>
        </div>
      </div>
    </div>
  </aside>
</template>

<script>
export default {
  props: ['toggle', 'cart', 'inventory'],
  computed: {},
  methods: {
    getPrice(name) {
      const product = this.inventory.find(pdt => {
        return pdt.name === name;
      })
      return product.price.USD
    },
    cartTotal() {
      let total = 0;
      for (let item in this.cart) {
        // item = clé de l'objet = nom
        total += this.cart[item] * this.getPrice(item);
      }
      return total.toFixed(2);
    },
    removeItem(name) {
      delete this.cart[name];
    }
  },
}
</script>