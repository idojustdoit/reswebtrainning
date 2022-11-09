<template>
	<section>
		<ul>
            <li v-for="(ItemList, index) in propsdata" v-bind:key="ItemList" class="shadow">
	<i class="checkBtn fa fa-check" aria-hidden="true"></i>
	{{ ItemList }}
	<span class="removeBtn" type="button" @click="removeItem(ItemList, index)">
		<i class="fa fa-trash-o" aria-hidden="true"></i>
	</span>
</li>
		</ul>
	</section>
</template>

<script>
export default {
    props: ['propsdata'],
	data() {
		return {
			ItemLists: []
		}
	},
	created() {
		if (localStorage.length > 0) {
			for (let i = 0; i < localStorage.length; i++) {
				this.ItemLists.push(localStorage.key(i));
			}
		}
	},
    methods: {
	removeItem(ItemList, index) {
		this.$emit('removeItem', ItemList, index);
	}
},
}
</script>


<style>
	ul {
		list-style-type: none;
		padding-left: 0px;
		margin-top: 0;
       text-align: center;       
	}
	li {
		
		display: inline-block;
		min-height: 50px;
		height: 50px;
		line-height: 50px;
		margin: 0.5rem 0;
		padding: 0 0.9rem;
		background: white;
		border-radius: 5px;
	}
	.checkBtn {
		line-height: 45px;
		color: #62acde;
		margin-right: 5px;
	}
	.removeBtn {
        cursor: pointer;
		margin-left:10px;
		color: #de4343;
	}
</style>