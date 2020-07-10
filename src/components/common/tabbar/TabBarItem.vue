<template>
    <div class="tab-bar-item" @click="itemClick">
      <div v-if="!isActive">
        <slot name="tab-bar-item"></slot>
      </div>
      <div v-else>
        <slot name="tab-bar-item-active"></slot>
      </div>
      <div :style="styleActive">
        <slot name="tab-bar-item-text"></slot>
      </div>
    </div>
</template>

<script>
    export default {
        name: "TabBarItem",
      props:{
          path:String,
        colorActive:{
            type:String,
          default:'pink'
        }
      },
      methods:{
          itemClick(){
            this.$router.replace(this.path)
          }

      },
      computed:{
          isActive(){
            return this.$route.path.indexOf(this.path)!==-1
          },
        styleActive(){
            return this.isActive?{color:this.colorActive}:{}
        }
      }
    }
</script>

<style scoped>
  .tab-bar-item{
    flex:1;
    text-align: center;
    font-size: 14px;
    height: 49px;
  }
  .tab-bar-item img{
    width: 24px;
    height: 24px;
    margin-top: 3px;
    vertical-align: middle;/**设置元素的垂直对齐方式**/
    margin-bottom: 2px;
  }

</style>
