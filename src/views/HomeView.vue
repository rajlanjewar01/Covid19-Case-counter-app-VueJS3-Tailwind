<template>
  <div v-if="!loading">
    <DataTitle :text="title" :date="date"/>
    <DataBox :stats="stats"/>
  </div>
  <div v-else class="flex items-center justify-center flex-col">
    content loading...
    <img :src="loadingImg"/>
  </div>
</template>

<script>
import DataTitle from '@/components/DataTitle';
import DataBox from '@/components/DataBox';
export default {
  name: 'HomeView',
  components: {
    DataTitle,
    DataBox,
  },
  data(){
    return{
      loading: true,
      title: 'Global',
      date: '',
      stats: {},
      country: [],
      loadingImg: require('../assets/loader.gif')
    }
  },
  methods:{
    async fetchResponse(){
      const response = await fetch('https:api.covid19api.com/summary');
      const data = await response.json();
      return data;
    },
  },

  async created(){
    const data = await this.fetchResponse()
    this.date = data.Date;
    this.stats = data.Global;
    this.country = data.country;
    this.loading = false;
  }
}
</script>
