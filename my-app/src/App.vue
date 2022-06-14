<template>
  <SearchBar @termChange="onTermChange" />
  <VideoList :videos="videosArray" />
  <!-- {{ videos.length }} -->
</template>

<script>
import { axios } from 'axios';
//import { response } from 'express';
import SearchBar from './components/SearchBar.vue';
import VideoList from './components/VideoList.vue';
const API_Key = 'AIzaSyCTa5xnVr0LPKoInVXiGU4hPlB09eMmYqs';

export default {
  name: 'App',
  components: {
    SearchBar: SearchBar,
    VideoList
  },
  data() {
    return {
      videosArray: []
    };
  },
  methods: {
    onTermChange(searchTerm) {
      axios.get('https://googleapis.com/youtube/v3/search', {
        params: {
          key: API_Key,
          type: 'video',
          part: 'snippet',
          q: searchTerm
        }
      }).then(response => {
        this.videos = response.data.items;
      })
    }
  }
}
</script>

<!-- <style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #aa0c0c;
  margin-top: 60px;
}
</style> -->
