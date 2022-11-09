<template>
  <div id="app">
		<Header></Header>
		<Inputcheck v-on:addItem="addItem"></Inputcheck>
    <List v-bind:propsdata="ItemLists" @removeItem="removeItem"></List>
		<Footer v-on:removeAll="clearAll"></Footer>
  </div>

</template>

<script>
import Header from './components/Header.vue'
import Input from './components/Input.vue'
import List from './components/List.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    'Header': Header,
		'Inputcheck': Input,
		'List': List,
		'Footer': Footer
  },
  data() {
	  return {
		ItemLists: []
	  }
  },
  methods:{
    addItem(ItemList){
   localStorage.setItem(ItemList, ItemList);
   this.ItemLists.push(ItemList)
},
      removeItem(ItemList, index) {
      localStorage.removeItem(ItemList);
      this.ItemLists.splice(index, 1)
   },
   clearAll() {
      localStorage.clear();
      this.ItemLists = [];
  }

  }
}

</script>

<style>
	body {
		text-align: center;
		background-color: #F6F6F8;
	}
	input {
		border-style: groove;
		width: 200px;
	}
	button {
		border-style: groove;
	}
	.shadow {
		box-shadow: 5px 10px 10px rgba(0, 0, 0, 0.03)
	}
</style>
