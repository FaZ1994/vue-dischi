<template>
  <div class="container">
    <app-loader v-if="loading" />
    <app-search-artist @search="searchedText" />
    <!-- <app-search-genre @search="searchedText" /> -->
    <div class="grid-container">
      <div v-for="(item, index) in filteredItems" :key="index" class="grid-item">
        <app-card :item="item" />
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import AppLoader from "./AppLoader.vue";
import AppCard from "./AppCard.vue";
import AppSearchArtist from "./AppSearchArtist.vue";
//import AppSearchGenre from "./AppSearchGenre.vue";

export default {
    name:"AppGrid",
    components:{
        AppLoader,
        AppCard,
        AppSearchArtist,
        //AppSearchGenre
        
    },
    data(){
        return {
            AlbumsItems:[],
            searchText: '',
            apiPath: "https://flynn.boolean.careers/exercises/api/array/music",
            loading: false,
        }
    },
    methods: {
        searchedText(txt){
            this.searchText = txt;
        }

    },

    computed:{
        filteredItems(){
            if (this.searchText === '') return this.AlbumsItems;
            return this.AlbumsItems.filter((item)=>item.title.toLowerCase().includes(this.searchText.toLowerCase()))

        }
    },
        mounted(){
        this.loading = true;
        axios.get(this.apiPath).then((res)=>{
            this.AlbumsItems = res.data.response
            this.loading = false;
        }).catch((error)=>{
            console.log(error)
            this.loading = false;
        })
    },
    props: {
    msg: String
  }
}
</script>

<style lang="scss" scoped>
.container {
    width: 80vw;
    padding: 7.5rem 0;
}

.grid-container {
  display: grid;
  grid-template-columns: auto auto auto auto auto;
  padding: 1em;
}

.grid-item {
    margin-bottom: 2em;
}

</style>

