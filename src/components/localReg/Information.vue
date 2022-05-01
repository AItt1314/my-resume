<template>
    <div id='educate'>
        <transition appear name="fade">
            <div v-if="status">
                <div class="title">教育</div>
                <div class="information main module">
                    <div><img src="../../assets/img/cdut.png" alt=""></div>
                    <div>
                        <h3 style="font-size:30px; color: #b3e19d">我是王保玉</h3>
                        <div class="my_inf">目前就读于 <span class="school">成都理工大学信息管理与信息系统专业</span> 将于2023年6月毕业，希望能找到一份前端方面实习工作。</div>
                    </div>
                </div>
            </div>
        </transition>
    </div>
</template>

<script>
export default {
    props:['status'],
}
</script>


<style scoped>
#educate{
    height: 670px;
    background-color: #F5F7FA;
}
.my_inf{
    margin-top: 60px;
    width: 500px;
    font-size: 20px;
    text-indent: 40px;
}
.school{
    font-style: italic;
    color: pink;
}
img{
    width: 500px;
}
</style>