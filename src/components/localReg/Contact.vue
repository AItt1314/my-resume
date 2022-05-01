<template>
<div class="contact">
    <transition name="slide-fade">
    <table v-if='isOpen'>
        <tr>
            <td>
                电话：
            </td>
            <td>
                15984073612
            </td>
        </tr>
        <tr>
            <td>
                微信：
            </td>
            <td>
                15984073612
            </td>
        </tr>
        <tr>
            <td>邮箱:</td>
            <td>2368724272@qq.com</td>
        </tr>
    </table>
    </transition>
</div>
</template>


<script>
export default {
    props: ['isOpen']
}
</script>


<style scoped>
.contact{
    position: absolute;
    top: 450px;
    left: 250px;
    width: 500px;
}
td{
    width: 100px;
    font-size: 30px;
    color:  #95d475;
}
.slide-fade-enter-active {
  transition: all 0.3s ease-out;
}

.slide-fade-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateX(10px);
  opacity: 0;
}
</style>