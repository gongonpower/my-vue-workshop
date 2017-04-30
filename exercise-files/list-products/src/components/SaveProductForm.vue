<template>
    <form action="">
        <div class="form-group">
            <label for="productName">Product name</label>
            <input id="productName" class="form-control" type="text" v-model="product.name" maxlength="32" placeholder="Enter product name">
        </div>
        <div class="form-group">
            <label for="productDescription">Product description <small class="text-muted">(optional)</small> </label>
            <textarea id="productDescription" class="form-control" v-model="product.description" maxlength="128" rows="3" placeholder="Enter description"></textarea>
        </div>
        <div class="form-group">
            <label for="price">Price</label>
            <input id="price" class="form-control" type="number" v-model="product.price" placeholder="Enter price">
        </div>
        <button class="btn btn-primary" type="submit" v-on:click.prevent="onSubmit">Save product</button>
    </form>
</template>
<script>
export default {
    props: ['product'],
    methods: {
        onSubmit() {
            this.$emit('submit', this.product);
        }
    }
}
</script>
