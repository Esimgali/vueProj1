<template>
    <div>
      <h4>Сколько раз было открыта пост {{ open_count }}</h4>
      <h4>Сколько постов было прочитано {{ read_count }}</h4>
      <div v-for="item in newsList">
        <News 
        :item="item" 
        :open="item.open"
        @open-news="openCount"
        @read_news="readCount"
        @unread_news="unreadCount"
        ></News>
      </div>
    </div>
   
  </template>
  
  
  <script>
  import News from './components/News.vue'
  export default {
    data (){
      return {
        now: new Date().toLocaleDateString(),
        newsList: [
          {
            key: "dragon",
            id: 1,
            title: "New anime",
            open : false,
            was_read: false
          },{
            key:"second",
            id: 2,
            title: "Rick and Morty",
            open : false,
            was_read: false
          }
        ],
        open_count: 0,
        read_count: 0
      }
    },
    provide(){
      return{
        news: this.newsList
      }
    },
    methods:{
      openCount(){
        this.open_count++
      },
      readCount(id){
        this.read_count++
        const idx = this.newsList.findIndex(news => news.id === id)
        this.newsList[idx].was_read = true
      },
      unreadCount(id){
        this.read_count--
        const idx = this.newsList.findIndex(news => news.id === id)
        this.newsList[idx].was_read = false
      }
  },
    computed:{
      openPost(){
        this.open = !this.open
        return open
      }
    },
    components:{ News }
  }
  </script>
  
  <style>
  
  </style>
  