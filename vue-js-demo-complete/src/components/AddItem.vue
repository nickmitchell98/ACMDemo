<!--Step 32: Create AddItem.vue-->
<template>
<div>
<!--Step 33: add form-->
<!--Step 39: @submit-->
<form @submit.prevent="addItem" class ="formAdd">
    <!--Step 38 add v-model title-->
    <input class = "itemText" type="text" v-model="title" name="title" placeholder = "Add Item...">
    <input type="submit" value="Submit" class = "btn">
</form>

</div>
    
</template>

<script>
//step 41: npm install uuid and import here
//import uuid from 'uuid';
import { v4 as uuidv4 } from 'uuid';

export default {
    //Step 34: add name
    name: "addItem",
    //Step 37: add function data()
    data() {
        return {
            title: ''
        }
    },
    //step 40: add Method
    methods: {
        addItem(e) {
            e.preventDefault();
            const newItem = {
                id: uuidv4(),
                title: this.title,
                purchased: false
            }
            //Step 41: send to parent
            this.$emit('add-item', newItem);
            this.title = '';
        }
    }
}
</script>

<!--Step 35: import CSS-->
<style scoped>
    .formAdd {
        display: flex;
    }

    .itemText {
        flex: 10;
        padding: 5px;
    }

    .btn {
        flex: 2;
    }

</style>