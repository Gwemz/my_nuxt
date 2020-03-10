<template>
    <div>
        {{msg}}
        <h2>地区：{{area}}</h2>
        <h3>条件：{{filter}}</h3>
    </div>
</template>
<script>
export default {
    head(){
        return {
            title: this.title
        }
    },
    data(){
        return {
            title: '',
            msg: '筛选条件',
            area: '',
            filter: ''
        }
    },
    asyncData({route}){             //服务端渲染函数
        console.log(route.params);
        let params = route.params;
        return {
            area: params.area,
            filter: params.filter,
            title: '大锅`s page'
        }
    },
    mounted(){
        // console.log(this.$route.params);
        // let params = this.$route.params;
        // this.area = params.area;
        // this.filter = params.filter;
        // this.title = 'not server page';
    }
}
</script>
<style>
h2,h3{
    font-size: 24px;
    text-align: center;
    line-height: 50px;
}
</style>