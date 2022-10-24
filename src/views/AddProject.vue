<template>
    <div class="card">
  
  <form @submit.prevent="handleSubmit">
    <div class="field">
     
      <input autocomplete="off" placeholder="title" class="input-field" name="logemail" type="title" v-model="title" required>
    </div>
    <div class="field">
    
      <input autocomplete="off"  placeholder="details" class="input-field" name="details" type="details" v-model="details" required>
    </div>
    <button class="btn" @click="handleSubmit()">Add Project</button>
   
  </form>

</div>
  
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
        }).then(() => {
            this.$router.push('/')
        }).catch((err) => console.log(err))
        }
       
    }

}
</script>

<style>
/* From uiverse.io by @alexruix */
.card {
 width: 100%;
 padding: 2.0rem 0.0rem;
 text-align: center;
 background: #2a2b38;
 height:10%;
 display: flex;
 justify-content: center;
 align-items: center;
 left:0;
 right:0;
 margin-top: 20rem;
}

/*Inputs*/
.field {
 margin-top: .5rem;
 display: flex;
 align-items: center;
 justify-content: center;
 gap: .5em;
 background-color: #1f2029;
 border-radius: 4px;
 padding: .5em 1em;
 font-size:45px;
}

.input-icon {
 height: 1em;
 width: 1em;
 fill: #ffeba7;
}

.input-field {
 background: none;
 border: none;
 outline: none;
 width: 100%;
 color: #d3d3d3;
 font-size: 24px;
}

/*Text*/
.title {
 margin-bottom: 1rem;
 font-size: 1.5em;
 font-weight: 500;
 color: #f5f5f5;
}

/*Buttons*/
.btn {
 margin: 1rem;
 font-size: .8em;
 text-transform: uppercase;
 padding: 0.6em 1.2em;
 background-color: #ffeba7;
 color: #5e6681;
 box-shadow: 0 8px 24px 0 rgb(255 235 167 / 20%);
 transition: all .3s ease-in-out;
}

.btn-link {
 color: #f5f5f5;
 display: block;
 font-size: .75em;
 transition: color .3s ease-out;
}

/*Hover & focus*/
.field input:focus::placeholder {
 opacity: 0;
 transition: opacity .3s;
}

.btn:hover {
 background-color: #5e6681;
 color: #ffeba7;
 box-shadow: 0 8px 24px 0 rgb(16 39 112 / 20%);
}

.btn-link:hover {
 color: #ffeba7;
}


</style>