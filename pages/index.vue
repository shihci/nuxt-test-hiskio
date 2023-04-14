<script>
import axios from "axios";
export default {
  async asyncData(){
    console.log(1,"asyncData")
  
    return {
      
    }
  },
  beforeCreate(){
    console.log(2,"beforeCreate")
  },
  created(){
    console.log(3,"created")
  },
  data(){
    return{
      name:"tyei",
      res:[]
    }
  },
  fetchOnServer: false,
  async fetch(){
    this.res =await axios.get('https://vue-lessons-api.vercel.app/photo/list').then(res=>res.data);
    console.log(4,"fetch")
  },
  // activated() {
  //     // Call fetch again if last fetch more than 10 sec ago
  //     if (this.$fetchState.timestamp <= Date.now() - 10000) {
  //       this.$fetch()
  //     }
  // },
  mounted(){
    console.log(5,"mounted")
  },
  methods:{
    handClick(){
      this.name="etttyw";
    }
  }
  //name: 'IndexPage',
  
}
</script>
<template>
  
  <!-- <h1 @click="handClick">
    {{ name }}
  </h1> -->
  <div>
    <nuxt-link to="/">Home</nuxt-link>
    <nuxt-link to="/about">About</nuxt-link>

    <h1>
    {{ name }}
  </h1>
  <h2 v-if="$fetchState.pending">Loading....</h2>
  <h3 v-if="$fetchState.error">{{ $fetchState.error }}</h3>
    <img v-for="item in res" :key="item.url" :src="item.url" alt="">
  </div>

 


</template>

