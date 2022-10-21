<template>
    <form @submit.prevent="handleSubmit">
        <input type="text" v-model="title" placeholder="title" required>
        <textarea type="text" v-model="details" placeholder="details" required> </textarea>
        <button> Add Project</button>

    </form>
  
</template>

<script>
export default {
    data() {
        return {
            title:'',
            details:''
        }
    }, 
    methods: {
        handleSubmit() {
        let project = {
            title: this.title,
            details: this.details,
            complete: false
        }
        fetch('http://localhost:3000/projects', {
            method: 'POST', 
            headers: { 'Content-Type': 'application/json'},
            body: JSON.stringify(project)
        })
        }
       
    }

}
</script>

<style>

</style>