<template>
    <div>
        <div class="blog-title">这是我的博客标题</div>
        <nuxt />
    </div>
</template>
<style>
.blog-title{
    font-size: 24px;
    line-height: 100px;
    color: #333333;
    text-align: center;
    animation: 1s appear;
    cursor: pointer;
}
.blog-title:hover{
    /* background: orangered;
    animation: 2s showbg; */
}
@keyframes appear {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
@keyframes showbg{
    0%{
        background: orange;
    }
    100%{
        background: orangered;
    }
}
</style>
