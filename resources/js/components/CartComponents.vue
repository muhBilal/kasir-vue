<template>
    <div class="mt-5">
        <h1>Keranjang</h1>
        <table class="table table-striped">
            <thead>
                <tr>
                    <th scope="col">No</th>
                    <th scope="col">Name</th>
                    <th scope="col">Description</th>
                    <th scope="col">Price</th>
                    <th scope="col">Total</th>
                    <th>Action</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(product, index) in items" :key="index">
                    {{product}}
                    <th scope="row">{{index + 1}}</th>
                    <td>{{product.name}}</td>
                    <td>{{product.description}}</td>
                    <td>{{product.price}}</td>
                    <td>{{product.total}}</td>
                    <td>@twitter</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
export default {
    data() {
        return {
            
        }
    },

    props: ['items'],
}
</script>
