<template>
    <div class="container">
        <product-components-vue @addCart="HandleAddCart" />
        <cart-components-vue :items="items" />
    </div>
</template>

<script>
import ProductComponentsVue from './ProductComponents.vue';
import CartComponentsVue from './CartComponents.vue';

export default {
    data(){
        return {
            items: []
        }
    },
    components: {
        ProductComponentsVue,
        CartComponentsVue
    },
    methods: {
        HandleAddCart(item){
            // this.item = item
            console.log('itemExmple', item)
            // this.items.forEach((product) => {
            //     if (item.name == product.name) {
            //         product.total += 1
            //     }
            // }

            const name = item.name
            const same = this.items.find((product) => product.name == name)
            if (same) {
                console.log(same)
                let count = 0
                this.items.forEach((product, index) => {
                    if (product.name == item.name) {
                        product.total = ++count
                        // this.items.splice(index, 1)
                        this.items.push(item)
                        return
                    }
                })
            } else {
                this.items.push(item)
            }
        }
    }
}
</script>
