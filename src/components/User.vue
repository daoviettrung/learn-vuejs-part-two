<template>
    <div class="user">{{user.email}}</div>
</template>
<script>
export default {
    name : 'user',
    props:{
        user: Object 
    },
    data(){
        return{

        }
    },
}
</script>
<style>

</style>