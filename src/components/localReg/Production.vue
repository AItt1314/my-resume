<template>
    <div id='production' :style='{height:height + "px"}'>
        <transition appear name="fade">
            <div v-if="status">
                <div class="title">作品</div>
                <div class="my_production main module">  
                    <el-carousel :interval="4000" type="card" height="500px">
                        <el-carousel-item v-for="item in productionList" :key="item.id">
                        <a :href="item.href" target="_blank"><img :src="item.src" alt="" class="active"></a>
                        </el-carousel-item>
                    </el-carousel>
                </div>
            </div>
        </transition>
    </div>
</template>

<script>
export default {
    data () {
        return {
            productionList:[
                {
                    id:1,
                    src:require('../../assets/img/work-rms.png'),
                    href:'https://github.com/AItt1314/rms-page'
                },
                {
                    id:2,
                    src:require('../../assets/img/work-cdutpage.jpg'),
                    href:'https://github.com/AItt1314/my-cdut'
                },
                {
                    id:3,
                    //解决data中定义图片相对路径页面不显示的问题 require
                    src:require('../../assets/img/work-pingyougou.png'),
                    href:'https://github.com/AItt1314/pingyougou_pages'
                    //在vue中的链接地址前需要加上http：//,否者跳转的是本地地址加拼接，http://localhost:8080/http:/www.baidu.com
                },
            ]
        }
    },
    props:['status','height'],
}
</script>


<style scoped>
#production{
    background-color:   #fcd3d3;
}
.el-carousel__item {
  color: #475669;
  font-size: 14px;
  opacity: 0.75;
  line-height: 200px;
  margin: 0;
  text-align: center;
}
.el-carousel {
    width: 1200px;
}
a
,img{
    display: block;
    width: 640px;
    height: 426px;
    transition: all 1s;
}
.active:hover{
    transform: scale(1.3);
}
</style>