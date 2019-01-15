<template>
    <div>
        <router-view />
        <ul class="footer">
            <li class="icons"><router-link :to="{name: 'list'}">news</router-link></li>
            <li class="icons"><router-link :to="{name: 'user'}">profile</router-link></li>
        </ul>
    </div>
</template>
<script>
export default {
    name : 'home'
}
</script>
<style lang="scss" scoped>
li{
    list-style: none;
}
.footer{
    position: fixed;
    width: 100%;
    height: 60px;
    line-height: 60px;
    left: 0;
    bottom: 0;
    display: flex;
    flex-flow: row nowrap;
    justify-content: space-around;
}
.icons{
    
    font-size: 16px;
    flex: 1;
    text-align: center;
    border-top: 1px solid #20b7d191;
    a{
        color: #42b996;
        display: block;
        &.active{
            color: #fff;
            background: #0cafa2;
        }
    }
}
</style>
