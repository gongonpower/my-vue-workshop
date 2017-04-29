<template>
    <table class="table table-hover product-table">
	<thead>
	    <tr>
	        <th>Name</th>
	        <th>Description</th>
	        <th>Price</th>
	    </tr>
	</thead>
	<tbody>
	    <tr v-for="product in products" track-by="id">
		<td>{{product.name}}</td>
		<td>{{product.description}}</td>
		<td>{{product.price}}</td>
	    </tr>
	</tbody>
    </table>
</template>
<script>
export default {
    data(){
	return {
	    products: [
	    {
		id:'cc913',
		name:'COBOL 101 vintage',
		description: 'Learn COBOL with this vintage programming book',
		price : 399
	    },
	    {
		id:'bcd7',
		name:'Sharp C2719 curved TV',
		description: 'Watch TV like never before with the brand new curved ' +
		'screen technology',
		price : 1995
	    },
{
		id:'7270',
		name:'Remmington X mechanical  keyboard',
		description: 'Excellent for gaming and typing, this Remmington X',
		price : 595
	    }
	    ]
	}
    }
}
</script>
<style scoped>
.header {
    font-size: 4rem;
}

</style>
