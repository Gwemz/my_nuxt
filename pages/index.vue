<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">
        nuxt program
      </h1>
      <h2 class="subtitle">
        我的关于nuxt的项目
      </h2>
      <div class="links">
        <a
          href="/posts"
          target="_self"
          class="button--green"
        >
          posts
        </a>
        <!-- <nuxt-link to="/posts">posts</nuxt-link> -->
        <a
          class="button--grey"
          @click="btnclick"
        >
          <!-- GitHub -->
          btn_click
        </a>
      </div>
      <!-- <nuxt-link to="/posts">posts</nuxt-link> -->
      <transition name="bounce">
        <div class="fade_text" @click="textClick">this is transition part</div>
      </transition>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'
// import VueNotifications from 'vue-notifications'
export default {
  loading: true,
  // transition: 'test',
  // transition (to, from) {
  //   if (!from) { return 'slide-left' }
  //   return +to.query.page < +from.query.page ? 'slide-right' : 'slide-left'
  // },
  transition: {
    name: 'bounce'
  },
  components: {
    Logo
  },
  // head: {
  //   title: '我的nuxt项目'
  // },
  data(){
    return {
      title: '我的nuxt项目'
    }
  },
  head(){
    return {
      title: this.title,
      meta: [
        { hid: 'gwt_description', name: 'gwt_description', content: 'My program about nuxt' }
      ]
    }
  },
  asyncData(context){
    // console.log(context);
  },
  fetch(data){
    // console.log(data);
  },
  mounted(){
    // this.$nextTick(() => {
    //   this.$nuxt.$loading.start()

    //   setTimeout(() => this.$nuxt.$loading.finish(), 1000)
    // })
    // this.showLoginError()
    // console.log(VueNotifications);
  },
  methods: {
    btnclick(){
      console.log('aaa');
      this.$nuxt.$loading.start()
      setTimeout(()=>{
        this.$nuxt.$loading.finish()
      },1000)
    },
    textClick(){    //文本点击
      this.showLoginError();
    }
  },
  notifications: {
    showLoginError: { // You can have any name you want instead of 'showLoginError'
      title: 'Login Failed',
      message: 'Failed to authenticate',
      type: 'error' // You also can use 'VueNotifications.types.error' instead of 'error'
    }
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}

.links a{
  cursor: pointer;
}
.fade_text{
  font-size: 28px;
  color: #333333;
  line-height: 75px;
}
/* .fade-enter {
   opacity: 0;
 }
 .fade-enter-active {
   transition: opacity .7s;
 } */
.bounce-enter-active {
   animation: bounce-in .8s;
 }
 .bounce-leave-active {
   animation: bounce-out .5s;
 }
 @keyframes bounce-in {
   0% { transform: scale(0) }
   50% { transform: scale(1.5) }
   100% { transform: scale(1) }
 }
 @keyframes bounce-out {
   0% { transform: scale(1) }
   50% { transform: scale(1.5) }
   100% { transform: scale(0) }
 }
</style>
