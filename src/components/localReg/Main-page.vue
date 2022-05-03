<template>
    <div id="main_page" :style='{height:height + "px"}'>
        <transition appear name="fade">
            <div class="home_page main module" v-if="status">
                <div class="page_data">
                    <h1>你好</h1>
                    <h1>我是<span class="my_name">王保玉</span></h1>
                    <h1>Web Developer</h1>
                    <el-button type="primary" class="contact" size="large" @click="open">联系我吧</el-button>
                </div>
                <div class="page_img">
                    <img src="../../assets/img/home.png" alt="">
                </div>
                <contact :isOpen='isOpen'></contact>
            </div>
        </transition>
    </div>
</template>


<script>
import Contact from './Contact.vue';
export default {
    data () {
        return {
            isOpen:false
        }
    },
    props:['status','height'],
    components:{
        Contact
    },
    methods: {
        open(){
            this.isOpen=!this.isOpen
        }
    }
}
</script>


<style scoped>
#main_page{
    margin-top: 80px;
    background-color: #d9ecff;
}
h1{
    font-size: 50px;
    margin: 30px 0;
}
.my_name{
    margin: 0 10px;
    color:  #79bbff;
}

img {
    width: 500px;
}

</style>