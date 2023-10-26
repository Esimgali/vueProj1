<template>
  <div>
    <h3>Динамичекие компоненты</h3>
  </div>
  <Button @action="component='first'">Первый пост(ввод)</Button>
  <Button @action="component='second'">Второй пост(выбор anim)</Button>
  <Button @action="component='third'">Третий пост</Button>
  <KeepAlive>
  <component :is="setComp">
  </component>
  </KeepAlive>
</template>


<script>
import Button from './components/Button.vue'
import PostsFirst from './posts/PostsFirst.vue'
import PostsSecond from './posts/PostsSecond.vue'
import PostsThird from './posts/PostsThird.vue'
export default {
  data(){
    return{
    component:"first"
    }
  },
  computed:{
    setComp(){
      return "posts-" + this.component
    }
  },
components:{Button, PostsFirst, PostsSecond, PostsThird}
}
</script>

<style>

</style>
