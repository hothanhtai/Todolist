<template>
  <form @submit.prevent="handelSubmit">
    <label>Title:</label>
    <input type="text" v-model="title" required>
    <label>Detail:</label>
    <textarea required v-model="detail"></textarea>
    <button>Add Project</button>
    
  </form>
</template>

<script>
export default {
    data() {
        return {
            title: '',
            detail: ''
        }
    },
    methods: {
        handelSubmit(){
         let project={
            title: this.title,
            detail: this.detail,
            complete: false
         }
        fetch('http://localhost:3000/projects',
            {method : 'POST',
            headers:{'Content-Type':'application/json'},
            body:JSON.stringify(project)}
        
        ).then(()=>{
            this.$router.push('/')
        }).catch((err)=>console.log(err))
          
        }
    },
}
</script>

<style>
    form{
        background: white;
        padding: 20px;
        border-radius: 10px;
    }
    label{
        display: block;
        color: rgb(11, 158, 136);
        text-transform: uppercase;
        font-size: 18px;
        font-weight: bold;
        letter-spacing: 1px;
        margin: 20px 0 10px 0;
    }
    input{
        padding: 10px;
        border: 0.4px solid black;
      
        width: 100%;
        box-sizing: border-box;

    }
    input[type='text'] {
        font-size: 20px; 
        font-family: monospace; }
    textarea{
        font-size: 20px;
        border: 0.4px solid black;
        padding: 10px;
        width: 100%;
        box-sizing: border-box;
        height: 100px;
    }
    form button{
        display: block;
        margin: 20px auto 0;
        background: #00ce98;
        color: white;
        padding: 10px;
        border: 0;
        border-radius: 6px;
        font-size: 16px;
    }

</style>