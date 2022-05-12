<template>
    <select @change="changeOption" v-model="optionselected">
        <option value="" disabled>Choose an option here</option>
        <option value="option one">option one</option>
        <option value="option two">option two</option>
        <option value="option three">option three</option>
    </select>
</template>
<script>
    export default {
        name: 'Dropdown',
        data () {
            return {
                optionselected:'',
            }
        },
        methods:{
            changeOption(){
                this.$emit('choosenoption',this.optionselected)
            }
        }
    }
</script>