<!--Step 12: create this file-->
<template>
<!--Step 20: add css style-->
<!--Step 21: add v-bind condition for "checked-off" class-->
    <div class = "item-list" v-bind:class="{'checked-off':item.purchased}">
        <!--step 19 replace "Item List" with item.title-->
        <!--step 22: Add event checkbox-->
        <p>
            <input type = "checkbox" v-on:change="markComplete">
            {{item.title}}
            <!--Step 24: add button-->
            <!--Step 25 add button event -->
            <button @click="$emit('del-item',item.id)" class = "del">DELETE</button></p>
        <!--<p>Item List</p>-->
    </div>
</template>

<script>
export default {
    //step 13: add name and css styles
    //step 18: add prop
    //step 23: add method markComplete
    name: "ItemList",
    props: ["item"],
    methods: {
        markComplete() {
            this.item.purchased = !this.item.purchased;

        }
    }
}
</script>

<style scoped>

    .item-list {
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc dotted;

    }

    .checked-off {
        text-decoration: line-through;
    }

    .del {
        background: #ff0000;
        color: #ffffff;
        border: none;
        padding: 5px 10px;
    border-radius: 20%;
    cursor: pointer;
    float: right;
    }

</style>