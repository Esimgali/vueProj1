<template>
    <h3>Это второй пост</h3>
    <form @submit.prevent="submitCheckBox()">
        <h3>Выбери аниме которые тебе понравились</h3>
        <label>
            <input type="checkbox" v-model="choose" name="anim" value="hanter"/>Хантер
        </label>
        <label>
            <input type="checkbox" v-model="choose" name="anim" value="bibop"/>Бибоп
        </label>
        <label>
            <input type="checkbox" v-model="choose" name="anim" value="friren"/>Фрирен
        </label>
        <button type="sublit" >отправить</button>
    </form>
    </template>
    <script>
    export default{
        data(){
            return{
            choose: []
            }
        },
        methods:{
            submitCheckBox(){
                console.group("Выбранные аниме")
                for(let i =0; i < this.choose.length; i++){
                console.log(this.choose[i]);
                }
                console.groupEnd()
            }
        }
    }
    </script>