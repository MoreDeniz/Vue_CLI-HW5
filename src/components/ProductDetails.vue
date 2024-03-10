<template>
    <div class="products">
        <div class="product" v-for="product in products" :key="product.id">
            <h3>{{ product.name }}</h3>
            <p>${{ product.price }}</p>
            <!-- <p>{{ formattedPrice }}</p> -->
            <p>
                {{ product.available ? "Available" : "Out of stock" }}
            </p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ProductComp',
  
    data() {
        return {
            products: [
                {
                    id: 1,
                    name: "Product 1",
                    price: 17.00,
                    available: true
                },
                {
                    id: 2,
                    name: "Product 2",
                    price: 199.99,
                    available: false
                },
                {
                    id: 3,
                    name: "Product 3",
                    price: 230.70,
                    available: true
                },
                {
                    id: 4,
                    name: "Product 4",
                    price: 50.54,
                    available: true
                },
            ],
        };
    },
  
    // НЕ РАБОТАЕТ!
    computed: {
        formattedPrice() {
            const formatter = new Intl.NumberFormat('en-US', {
                style: 'currency',
                currency: 'USD',
            });
            return formatter.format(this.product.price);
        },
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