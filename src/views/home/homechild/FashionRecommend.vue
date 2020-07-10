<template>
    <div class="fashion-recommend">
      <div v-for="item in recommends" :key="item.index">
        <a :href="item.link">
          <img :src="item.image" alt="">
            <div>{{item.title}}</div>
        </a>
      </div>
    </div>
</template>

<script>
    export default {
        name: "FashionRecommend"
      ,
      props:{
          recommends:{
            type:Array,
            default() {
              return [];
            }
          }
      }
    }
</script>

<style scoped>
.fashion-recommend{
  width: 100%;
  display: flex;
  text-align: center;
  padding: 15px 0 20px;
  font-size: 14px;
  background-color: white;
}
  .fashion-recommend img{
    width: 85%;
    margin-bottom: 10px;
  }
</style>
