<template>
    <div id="inputWrapper">
        <input type="text" v-on:keyup.enter="submit" v-model="search">
    </div>
</template>

<script>
import eventBus from '../commons/eventBus'

export default {
    data(){
        return{
            search : null,            
        }
    },
    methods:{
        submit(){
            eventBus.$emit('submit', this.search);
        }
    }
}
</script>

<style>
#inputWrapper{
    display: flex;
    flex-direction: row;
    justify-content: center;
    width: 100%;
    border: 2px solid #63ace8;
}
#inputWrapper > input{
    width: 100%;
    font-size: 30px;
    padding-left: 20px;
}
input:focus{
    outline: none;
}
</style>
