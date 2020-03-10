<template>
    <div>
        shop
        {{route}}
    </div>
</template>
<script>
export default {
    data(){
        route: ''
    },
    asyncData({route}){
        // console.log(route.params);
        // return {
        //     route: this.$route
        // }
        return {
            route: route.params
        }
    },
    mounted(){
        // console.log(this.$route.params);
    }
}
</script>