<template>
    <div>
        <p>{{ textoption }}</p>
        <Dropdown @choosenoption="changestuff"/>
        <h1>Brands</h1>
        <ul v-for="brand in brands" :key="brand.id">
            <p>{{ brand.brand }}</p>
        </ul>
    </div>
</template>
<script>
    import Dropdown from './Dropdown.vue';
    import axios from "axios"
    export default {
        name: 'List',
        data () {
            return {
                textoption:'',
                brands:[]
            }
        },
        methods:{
            changestuff(value){
                this.textoption = value
            }
        },
        mounted(){
            axios.get('http://localhost/amad/api/brand')
            .then(resp=>{
                this.brands = resp.data;
                console.log(resp.data)
            })
            .catch(error=>{
                console.log(error)
            })
        },
        components:{
            Dropdown
        },
    }
</script>