<template>
  <ul>
    <learning-resource
      v-for="res in resources"
      :key="res.id"
      :description="res.description"
      :link="res.link"
      :title="res.title"
      :id="res.id"
    ></learning-resource>
  </ul>
</template>

<script>
import learningResource from './LearningResource.vue';
export default{
    // props:["resources"],
    inject:["resources"],
    components:{
        learningResource
    },
    data(){
        return{

        }
    }
}
</script>

<style scoped>
ul{
    list-style-type: none;
    padding:0;
    margin: 2rem auto;
    max-width: 500px;
}
</style>
