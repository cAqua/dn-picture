<template>
  <view @click=handleClick>
    
    <slot></slot>
  </view>
</template>

<script>
//组件功能  接收使用该组件页面图片和索引数据
// 并在单击的时候吧数据发给全局变量接收 并跳转
export default {  
  props:{
    list:Array,
    index:Number,
    params:Object,
    Imgid:''
  },
  methods:{
    handleClick(){
      getApp().globalData.imgList=this.list;
      getApp().globalData.imgIndex=this.index;

      if(this.params){
        getApp().globalData.params = this.params
        getApp().globalData.Imgid = this.Imgid
        
      }

      console.log(this.Imgid);


      uni.navigateTo({
        url:'/pages/ImgDetails/index'
      })



      
    }
  }

}
</script>

<style>

</style>