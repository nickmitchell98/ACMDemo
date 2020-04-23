<template>
<!--Main Component-->
  <div id="app">

    <!--Step 31: add header to Template-->
    <Header />
    <!--Step 42: v-on adds Item-->
     <AddItem v-on:add-item="addItem"/>
    <!--step 2: Get rid of logo and message-->
    <!--Embedded Component: HelloWorld showing message prop-->
    <!--step 9 use v-bind to export array to items-->
    <!--Step 27: add v-on condition-->
    <Items v-bind:items="items" v-on:del-item="deleteItem"/>
   
   
  </div>
</template>

<script>
//Step 30: Import Header.vue and add header to components
  import Header from'./components/layout/Header'; 

//Imports Component HelloWorld into App.vue

//Step 3: get rid of import and HelloWorld in components
//step 8: import items component and put <Items /> in template
  import Items from './components/Items';

//step 36: Import add Item, add to compunents and use it in Template
import AddItem from './components/AddItem';

export default {
  name: 'App',
  //Exports HelloWorld Component

  
  components: {
    Header,
    Items,
    AddItem
  },
  //Step 4: Add function data
  data() {
    return {
      //Step 5: add array
      items: [
        {
          id: 1,
          title: "Laptop",
          purchased: false
        },
        {
          id: 2,
          title: "3D Printer",
          purchased: false
        },
        {
          id: 3,
          title: "Apple",
          purchased: false
        }
      ]
      
    }
  },
  //Step 28: add delete method
  methods: {
    deleteItem (id) {
        this.items = this.items.filter(item => item.id != id);
    },
    //Step 43: add method (Spread object copies the array)
    addItem(newItem) {
        this.items = [...this.items, newItem];  
    }
  }
  
}
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1-4;
  }
  .btn {
	display: inline-block;
	border: none;
	background: #777;
	color: #FFFFFF;
	padding: 7px 20px;
	cursor: pointer;
  }

  .btn:hover {
	background: #888;
  }


</style>
