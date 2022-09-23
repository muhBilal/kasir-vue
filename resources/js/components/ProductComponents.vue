<template>
    <div class="mt-3">
        <h1>Produk</h1>
    <table class="table table-striped">
        <thead>
            <tr>
                <th scope="col">#</th>
                <th scope="col">nama</th>
                <th scope="col">Deskripsi</th>
                <th scope="col">Stok</th>
                <th scope="col">Harga</th>
                <th scope="col">Action</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="(item, index) in product" :key="item.name">
                <th >{{index +1 }}</th>
                <td>{{item.name}}</td>
                <td>{{item.description}}</td>
                <td>{{item.stock}}</td>
                <td>{{item.price}}</td>
                <td>
                    <button class="btn btn-primary" @click="addProduct(index)">Tambah</button>
                </td>
            </tr>
        </tbody>
    </table>
</div>
</template>

<script>
export default {
    name : 'Product',
    data(){
        return {
            product : [
                    {
                        name : "mi goreng",
                        description : "mi goreng merupakan mi instan",
                        stock : 10,
                        price : 2000
                    },{
                        name : "mi gelas",
                        description : "mi  kuah versi gelas",
                        stock : 5,
                        price : 1500
                    },{
                        name : "mi soto",
                        description : "mi instan rasa soto",
                        stock : 12,
                        price : 2500
                    },
            ]
        }
    },
    methods: {
        addProduct(index){
            this.product.forEach((item, index2) => {
                console.log('itemProduct', item)
                    if(index2 == index && item.stock > 0) {
                        item.stock -= 1;
                        console.log('itemProduct', item)
                        this.$emit('addCart', item);
                        // return item;e
                    }
               });

        }
    }
}
</script>
