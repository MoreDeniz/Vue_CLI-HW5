<template>
    <div class="products">
        <div class="product" v-for="product in products" :key="product.id">
            <h3>{{ product.productName }}</h3>
            <h5>price: {{ product.productPrice }}</h5>
            <p>{{ product.available }}</p>
        </div>
    </div>
</template>

<script>
export default {
  name: 'ProductComp',
  
  props: {
 
  },

  data() {
    return {
      products: [
        {
            id: 1,
            productName: "Product 1",
            productPrice: 1700,
            available: "Available"
        },
        {
            id: 2,
            productName: "Product 2",
            productPrice: 1200,
            available: "Out of stock"
        },
        {
            id: 3,
            productName: "Product 3",
            productPrice: 2300,
            available: "Available"
        },
        {
            id: 4,
            productName: "Product 4",
            productPrice: 500,
            available: "Available"
        },
      ],
    };
  },

  methods: {
     
  },
}

</script>
    
<style scoped>
    .products {
        display: flex;
        gap: 30px;
    }

    .product {
        width: 200px;
        height: 150px;
        border: 1px solid rgb(10, 12, 124);
    }
</style>