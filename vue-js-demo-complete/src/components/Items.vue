<!--Step 5: create this file-->
<template>
<!--Step 6: Add root element(div) and h1-->
    <div>
        <!--Step 11 delete h1 add v-for div-->
        <div v-bind:key="item.id" v-for="item in items" >
            <!--Step 16: delete h3 commented in complete demo-->
            <!-- step 17: Add v-bind-->
            <!--Step 26: add v-on condition-->
            <ItemList v-bind:item="item" v-on:del-item="$emit('del-item', item.id)"/>
            <!--<h3>{{item.title}}</h3>-->
        </div>
    </div>
</template>

<script>
//step 14 import ItemList.vue
import ItemList from './ItemList.vue'

//Step 10 add prop to Items from App.vue
export default {
    //Step 7: add component name
    //step 15 add components section
    name: "Items",
    components: {
        ItemList
    },
    props: ["items"]
    
}
</script>

<style scoped>

</style>