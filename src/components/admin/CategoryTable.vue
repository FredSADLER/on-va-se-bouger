<template>
    <tr>
        <td>{{id}}</td>
        <td :id="'name->'+id" contenteditable="true">{{name}}</td>
        <td><button class="btn btn-outline-secondary" @click="updateCategory(id)">Update</button></td>
        <td><button class="btn btn-outline-dark" @click="deleteCategory(id)">Delete</button></td>
    </tr>
</template>
<script>

export default {
    props: {
        id: String,
        name: String,
    },
    methods: {
        deleteCategory(_id){
            this.$store.dispatch('deleteCategory', _id)
        },
        updateCategory(_id) {
            const category_name = document.getElementById('name->'+_id).innerText;
            this.$store.dispatch('updateCategory', {_id, category_name})
        }
    },
}
</script>
<style>
</style>