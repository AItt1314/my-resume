<template>
<div >
  <my-header></my-header>
  <main-page :status='again[0].status'></main-page>
  <information :status='again[1].status'></information>
  <my-skills :status='again[2].status'></my-skills>
  <production :status='again[3].status'></production>
</div>
</template>

<script>
import MyHeader from './components/localReg/Myheader.vue';
import MainPage from './components/localReg/Main-page.vue';
import Information from './components/localReg/Information.vue';
import MySkills from './components/localReg/Myskills.vue';
import Production from './components/localReg/Production.vue'
import Footer from './components/localReg/Footer.vue';


export default {
  data () {
    return {
      //控制下模块是否渲染，通过页面被卷曲的高度
      again:[
        {id:1,status:true},
        {id:2,status:false},
        {id:3,status:false},
        {id:4,status:false}
      ]
    }
  },
  components:{
    MyHeader,MainPage,Information,MySkills,Production,Footer
  },
  methods:{
    //控制下模块是否渲染，通过页面被卷曲的高度
    anew(){
      console.log(111);
      this.again.forEach(element => {
        element.status = false;
        if(window.pageYOffset<550) {
            this.again[0].status=true
            }
             else if(window.pageYOffset<1650&&window.pageYOffset>=1100)
            {
                 this.again[2].status=true
            }
            else if(window.pageYOffset<1650&&window.pageYOffset>=550)
            {
                 this.again[1].status=true
            }
            else{
                this.again[3].status=true
            }
      })
    }
  },
  //生命周期钩子   渲染时挂载函数
  mounted () {
    window.addEventListener('scroll',this.anew)
  }
}
</script>

<style scoped>

</style>