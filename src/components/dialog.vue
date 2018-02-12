<template>
 <div>
     <!-- 这里添加通用的弹窗组件 -->
     <!-- 如登录，注册，关于等 -->
     <div class="dialogMainFrame">
        <div class="dialog-cover" @click="close" v-if="isShow"></div>
        <transition name="dialogCatton" >
            <div class="dialog-content" v-if="isShow">内容
                <div class="dialog-close">
                    <a href="#" @click="close"> x </a>
                </div>
            </div>
        </transition>
     </div>


 </div>
</template>

<script>
 export default {
   props: {
       isShow : {
           type : Boolean,
           required : true,
           default : false
       }
   },
   data () {
     return {

     }
   },
   components: {

   },
   methods: {
       close(){
           this.$emit('onClose'); //通知父组件关闭弹窗
       }
   }
 }
</script>

<style scoped>
.dialogCatton-enter{
    transform: translateY(700px);
}
.dialogCatton-enter-active{
    transition: all 0.5s ease;
}
.dialogCatton-leave-active{
    transition: all 0.5s ease;
    transform: translateY(-700px);
}


.dialogMainFrame{
    width: 100%;
    height: 100%;
    position: fixed;
}
.dialog-cover{
    background: #000;
    opacity: .3;
    position: fixed;
    z-index: 5;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}

.dialog-content{
    width: 50%;
    position: fixed;
    max-height: 50%;
    overflow: auto;
    background: #fff;   
    top: 20%;
    left: 50%;
    transform: translate(-50%);
    z-index: 10;
    border: 2px solid #464068;
    padding: 2%;
    line-height: 1.6;
    border-radius: 10px;
}
.dialog-close a{
    position: absolute;
    top: 1px;
    right: 5px;
    text-decoration: none;
}

 
</style>
