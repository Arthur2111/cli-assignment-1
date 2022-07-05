<template>
    <form>
        <div>
            <label>Username</label>
            <input type="text" placeholder="username" v-model="createUsername">
        </div>
        <div>
            <label>Age</label>
            <input type="text" placeholder="age" v-model="createAge">
        </div>
        <div>
            <label>ID</label>
            <input type="text" placeholder="ID" v-model="createID">
        </div>
        <button @click.prevent="$emit('create-new-user', createUsername,createAge,createID)">Submit</button>
    </form>
</template>

<script>
export default {
    data() {
        return {
            createUsername: '',
            createAge: '',
            createID:''
        }
    },




}
</script>