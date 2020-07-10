<template>
    <div class="tab-control">
      <div class="tab-control-item"
           :class="{active:index===currentIndex}"
           @click="itemClick(index)"
           v-for="(item,index) in title">
        <span>{{item}}</span>
      </div>
    </div>
</template>

<script>
    export default {
        name: "TabControl",
      data(){
          return{
            currentIndex:0

          }
      },
      props:{
          title:{
            type:Array,
            default(){
              return []
            }
          }
      },
      methods:{
          itemClick(index){
            this.currentIndex=index
          }
      }
    }
</script>

<style scoped>
.tab-control{
  text-align: center;
  display: flex;
  font-size: 14px;
  height: 44px;
  line-height: 44px;
  background-color: white;
  position: sticky;
  top:44px;

}

  .tab-control-item{
    flex:1
  }

.active{
    color:var(--color-high-text);
  }
  .active span{
    border-bottom: 1px solid var(--color-high-text);
    padding: 4px;
  }
</style>
