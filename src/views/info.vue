<template>
    <div>
        HELLO INFO componet
        <button type="button" @click="add()">add</button>
        <div>
            {{msg}}
        </div>
    </div>
</template>
<script>
import store from '@/store'
export default {
    name: 'Info',
    data() {
        return {
            msg:'my vue '
        }
    },  
    store,
    methods: {
        add(){
            console.log('add an elements');
            store.commit('increase');
        },
    },
}
</script>   
<style lang="">
    
</style>