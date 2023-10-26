<template>
 <div class="listOfNews">
    <h3>{{ item.title }}</h3>
    <Button @action="openNews()">{{newOpen ? "close" : "open"}}</Button>
    <div  v-if="newOpen">
    <p>yuvbiunimo,l;.</p>
    <Button @action="read_post()" v-if="!item.was_read">Прочитать пост</Button>
    <Button @action="unread_post()" v-if="item.was_read">Сделать непрочитанным</Button>
    <NewsList></NewsList>
    </div>
  </div>
</template> 
<script>
import Button from "./Button.vue"
import NewsList from "./NewsList.vue"
export default{
    props:{
        item: {
            type: Object,
            required: true,
        },
        open: {
            type:Boolean,
            required: false,
            default: false
        }
    },
   // emits:['open-news'],
   emits:{
    'open-news': null,
    "read_news"(news_id){
        if(news_id){
            console.log(news_id)
            return true
        }
        return false
    },
    'unread_news'(news_id){
        if(news_id){
            console.log(news_id)
            return true
        }
        return false
    }
   },
    data(){
        return{
            newOpen: this.open
        }
    },
    methods:{
        openNews(){
            this.newOpen =  !this.newOpen
            if(this.newOpen){
                this.$emit('open-news')
            }
        },
        read_post(){
            this.item.was_read = true
            console.log("Пост номером ", this.item.id , "было прочитано")
            this.$emit('read_news', this.item.id)
        },
        unread_post(){
            this.item.was_read = false
            this.$emit('unread_news', this.item.id)
        }
    },
    components:{Button, NewsList}
}
</script>