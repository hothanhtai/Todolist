<template>
   <form @submit.prevent="handelSubmit">
    <label>Title:</label>
    <input type="text" v-model="title" required>
    <label>Detail:</label>
    <textarea required v-model="detail"></textarea>
    <button>Update Project</button>
  </form>
</template>

<script>
export default {
    props:['id'],
    data() {
        return {
            title: '',
            detail: '',
            uri: 'http://localhost:3000/projects/'+ this.id
        }
    },
    mounted() {
        fetch(this.uri)
            .then(res=> res.json())  
            .then(data => {
                this.title=data.title,
                this.detail=data.detail
            })
    },
    methods: {
        handelSubmit(){
            fetch(this.uri,{
                method: 'PATCH', 
                headers:{'Content-Type':'application/json'},
                body:JSON.stringify({ title: this.title, detail: this.detail})
            }).then(()=> {
            this.$router.push('/')})
            .then(err=> console.log(err))
        }
    },
}
</script>

<style>

</style>