<template>
    <section>
        <save-product-form :product="productInForm" v-on:submit="onFormSave"></save-product-form>
        <product-list :products="products" v-on:edit="onEditClicked"></product-list>
    </section>
</template>
<script>
import uuid from 'uuid';
import ProductList from './ProductList'
import SaveProductForm from './SaveProductForm'

const initialData = () => {

    return {
        productInForm: {
            id: null,
            name: '',
            description: '',
            price: null
        },
        products: [{
                id: 'cc913',
                name: 'COBOL 101 vintage',
                description: 'Learn COBOL with this vintage programming book',
                price: 399
            },
            {
                id: 'bcd7',
                name: 'Sharp C2719 curved TV',
                description: 'Watch TV like never before with the brand new curved ' +
                    'screen technology',
                price: 1995
            },
            {
                id: '7270',
                name: 'Remmington X mechanical  keyboard',
                description: 'Excellent for gaming and typing, this Remmington X',
                price: 595
            }
        ]

    }
}
export default {
    components: {
        ProductList,
        SaveProductForm
    },
    data: initialData,
    methods: {
        onFormSave(productData) {
            const index = this.products.findIndex((p) => p.id === productData.id);
            if (index !== -1) {
                this.products.splice(index, 1, productData);
            } else {

                productData.id = uuid.v4();
                this.products.push(productData);
            }
            this.resetProductInForm();
        },
        resetProductInForm() {
            this.productInForm = initialData().productInForm;
        },
        onEditClicked(productData) {
            this.productInForm = { ...productData
            };
        }

    }
}
</script>
