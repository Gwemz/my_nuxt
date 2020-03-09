<template>
  <div :class="msg">
      <h2>每日一言</h2>
      <ul>
          <li>一言标识:{{datas.id}}</li>
          <li>一言正文:{{datas.hitokoto}}</li>
          <li>一言类型:{{datas.type}}</li>
          <li>一言出处:{{datas.from}}</li>
          <li>一言作者:{{datas.from_who}}</li>
          <li>添加者:{{datas.creator}}</li>
          <li>唯一标识:{{datas.uuid}}</li>
          <li>添加时间:{{datas.created_at}}</li>
      </ul>
  </div>
</template>

<script>
import axios from 'axios'
export default {
    // loading: false,
    transition (to, from) {
        if (!from) { return 'slide-left' }
        return +to.query.page < +from.query.page ? 'slide-right' : 'slide-left'
    },
    layout: 'blog',
    middleware: 'tongji',
    data(){
        return {
            datas: '',       //每日一言信息
            msg: 'post_container',
        }
    },
    async asyncData({params}){
        // console.log(params);
        let { data } = await axios.get(`https://v1.hitokoto.cn/`);
        // console.log(data);
        // this.datas = data;
        return {
            datas: data
        }
    },
    mounted(){
        // this.$nextTick(() => {
        // this.$nuxt.$loading.start()

        // setTimeout(() => this.$nuxt.$loading.finish(), 5000)
        // })
        // setTimeout(()=>{
        //     this.$nuxt.$loading.finish()
        // },1000)
    },
    // router: {
    //     middleware: 'tongji'
    // }
}
</script>

<style>
.post_container{
    width: 800px;
    margin: 0 auto;
    line-height: 50px;
}
.post_container h2{
    text-align: center;
    font-size: 24px;
}
</style>