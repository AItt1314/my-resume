<template>
    <div id='my_skills' :style='{height:height + "px"}'>
        <transition appear name="fade">
            <div v-if="status">
                <div class="title">技能</div>
                <div class="my_skills main module">
                    <div>
                        <h3 class="skills_title">Professional Skills</h3>
                        <div class="skills">熟练html/CSS/Javascript,了解jQuery和vue3.x，并能基于jQuery/vue3.x开发一些小项目，对node.js,webpack有所了解。</div>
                        <div class="skills_table">
                            <div class="per" v-for='item in skillTable' :key="item.id">
                                <div class="text">
                                    <span>{{item.title}}</span>
                                    <span>{{item.size}}</span>
                                </div>
                                <el-progress :percentage='item.length' :color='item.color' :text-inside=true :stroke-width="35" />
                            </div>
                        </div>
                    </div>
                    <div>
                        <img src="../../assets/img/work.jpg" alt="">
                    </div>
                    <div class="success">虽然我仍有很多不足，但是我会保持专注，继续学习！</div>
                </div>
            </div>
        </transition>
    </div>
</template>


<script>
export default {
    data () {
        return {
            skillTable:[
                {
                    id:1,
                    title:'HTML',
                    size:'95%',
                    length:95,
                    color:' #79bbff'
                },
                {
                    id:2,
                    title:'CSS',
                    size:'85%',
                    length:85,
                    color:' #95d475'
                },
                {
                    id:3,
                    title:'Javascript',
                    size:'80%',
                    length:80,
                    color:' #eebe77'
                },
                {
                    id:4,
                    title:'jQuery',
                    size:'75%',
                    length:75,
                    color:' #f89898'
                },
                {
                    id:5,
                    title:'VUE',
                    size:'75%',
                    length:75,
                    color:' #b1b3b8'
                },
            ],
        }
    },
    props:['status','height'],
}
</script>

<style scoped>
#my_skills{
    background-color:  #f8e3c5;
}
h3{
    font-size: 25px;
    color:  #529b2e;
    margin-bottom: 15px;
}
.skills{
    margin-bottom: 15px;
    font-size: 20px;
}
.skills_table .text {
    font-size: 18px;
    width: 500px;
    display: flex;
    justify-content: space-between;
}
.per {
    margin-bottom: 15px;
}
img{
    width: 400px;
}
.success{
    position: absolute;
    bottom: 20px;
    width: 100%;
    text-align: center;
    font-size: 30px;
    color: red;
}
</style>