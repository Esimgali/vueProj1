<template>
  <div>
    Счетчик  {{count}}
  </div>
  <button @click="count++"> inc</button>
  <div class="postsForm">
    <input class="input" type="text" v-model="inputValue" @input="inputText"  @keyup.shift.enter="addToList"/>
    <div id="inputText"></div>
    <button class="submit" @click="addToList">Add post</button>
    <ul class="postList"> 
      <li class="postItem" v-for="(post, idx) in list" :key="post.key">
        <div class="title">[{{ idx }}] {{ post.title }}</div>
        <input type="text" @click.stop ref="postInput"/>
        <button class="delete" @click="deletePost(idx)">Delete</button>
      </li>
    </ul>
  </div>
</template>


<script>
export default {
  data(){   
    return{ 
      count: 0,
      list: [],
      inputValue: ""
    }
  },
  methods: {
      inc(){this.count++},
      addToList(){
        console.log(this.inputValue);
        this.list.push({title: this.inputValue,key:new Date().toJSON()})
        this.inputValue = ""
      },
      inputText(event){
        console.log(event.target.value)
        document.getElementById("inputText").innerHTML = event.target.value;
      },
      deletePost(idx){
        console.log(idx, 1)
        this.list.splice(idx, 1)
      }
  }
  
}
</script>

<style>

</style>
