<template>
    <div>
        <div class="header">
            <div class="main">
                <a href="#" class="namer">王保玉</a>
                <div class="btn">
                    <a href="#" v-for='item in titleList' :key="item.id" @click.prevent="changeHeight(item.scrollY)" :class="{active:item.isActive}">{{item.title}}</a>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data () {
        return {
            titleList:[
        {
            id:1,
            title:'首页',
            isActive:true,
            scrollY:0,
        },
        {
            id:2,
            title:'教育',
            isActive:false,
            scrollY:(this.height-110)
        },
        {
            id:3,
            title:'技能',
            isActive:false,
            scrollY:(this.height-110)*2
        },
        {
            id:4,
            title:'作品',
            isActive:false,
            scrollY:(this.height-110)*3
        }],
    }
    },
    props:['height'],
    computed:{
        myHeight(){
            return this.height-110
        }
    },
    methods:{
        //根据页面被卷去的头部切换标签
        tagChange(){
            this.titleList.forEach(element => element.isActive=false);
            if(window.pageYOffset<this.myHeight) {
            this.titleList[0].isActive=true
            }
             else if(window.pageYOffset<this.myHeight*3&&window.pageYOffset>=this.myHeight*2)
            {
                 this.titleList[2].isActive=true
            }
            else if(window.pageYOffset<this.myHeight*2&&window.pageYOffset>=this.myHeight)
            {
                 this.titleList[1].isActive=true
            }
            else{
                this.titleList[3].isActive=true
            }
        },
        changeHeight(Y){
            window.scrollTo(0,Y)
        }
    },
    //整页翻动效果
    mounted () {
        window.addEventListener('scroll',this.tagChange)
        if (document.addEventListener) {
        //火狐使用DOMMouseScroll绑定
        document.addEventListener("DOMMouseScroll", (e)=>{
             if (e.detail > 0) {
            //当滑轮向上滚动时
  			//  console.log("向上滚动")
           window.scrollTo(0,window.pageYOffset-this.myHeight)
          }else if (e.detail < 0) {
            //当滑轮向下滚动时
 			// console.log("向下滚动")
             window.scrollTo(0,window.pageYOffset+this.myHeight)
          }
        }, false);
      }
      //其他浏览器直接绑定滚动事件
      window.addEventListener('mousewheel',(e)=>{
          //判断浏览器IE，谷歌滑轮事件
          if (e.wheelDelta > 0) {
            //当滑轮向上滚动时
            // console.log("向上滚动")
           window.scrollTo(0,window.pageYOffset-this.myHeight);
          }else if(e.wheelDelta < 0){
			// console.log("向下滚动")
            window.scrollTo(0,window.pageYOffset+this.myHeight);
            }
      },false)
    }
    }
</script>





<style scoped>
.header{
    /* 固定定位 */
    position: fixed;
    top: 0;
    right: 0;
    z-index: 999;
    background-color: #fff;
    height: 80px;
    width: 100%;
    box-shadow: 0 1px 4px rgb(146 161 176 / 15%);
}
a{
    position: relative;
    display: inline-block;
    line-height: 80px;
    margin: 0 50px;
    color: black;
}
.btn .active::after{
    position: absolute;
    content: "";
    width: 50px;
    height: 3px;
    left: -5px;
    bottom: 10px;
    background-color: #409EFF;
}
.btn{
    float:right;
}
</style>

