<template>
   
        <div class="inputBox shadow">
         <input type="text" v-model="newItem" placeholder="Insert Text" v-on:keyup.enter="addItem">
         <span class="addContainer" v-on:click="addItem">
               <i class= "addBtn fa fa-plus" aria-hidden="true"></i>
         </span>
  
    </div>
    
  </template>
  
  <script>
  export default {
      data() {
          return {
                newItem: ''
             }
         },
      methods: {
        addItem() {
	if (this.newItem !== "")  {
		let value = this.newItem && this.newItem.trim();
		this.$emit('addItem', value)
        this.clearInput();
	}
},
          clearInput() {
              this.newItem = '';
          }
      }
  }
  </script>
  
  <style scoped>
      input:focus {
          outline: none;
        
      }
      .inputBox {
        margin: auto;
         display: block;
          background: white;
          height: 50px;
          line-height: 50px;
          border-radius: 5px;
          width:255px;
      }
      .inputBox input {
          border-style: none;
          font-size: 0.9rem;
      }
      .addContainer {
        cursor: pointer;
          background: linear-gradient(to right, #6478FB, #8763FB);
          display: inline-block;
          width: 3rem;
          border-radius: 0 5px 5px 0;
      }
      .addBtn {
          color: white;
          vertical-align: middle;
        
      }
  </style>