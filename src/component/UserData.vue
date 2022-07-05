<template>
<!-- if the page is reloaded the data is also reloaded and would be created and quickly refreshed -->
    <form  >
    <div>
        <label>Username</label>
        <input type="text" v-model="enteredUsername">
    </div>
    <div>
        <label>Age</label>
        <input type="text" v-model="enteredAge">
    </div>
    <div>
        <label>ID</label>
        <input type="text" v-model="enteredID">
    </div>
    <button @click.prevent="submitData">Submit</button>
    </form>
</template>
a
<script>

export default {
    emit: ['set-user'],
    data () {
        return {
            enteredUsername: '',
            enteredAge: '',
            enteredID: ''
        }
    },
    methods: {
        submitData() {
            this.$emit('set-user', this.enteredUsername, this.enteredAge, this.enteredID)
        }
    }
}

</script>