<template>
    <h3>Это третий пост</h3>
    <form @submit.prevent="submitRadio()">
        <h3>Выбери свое первое аниме</h3>
        <ul>
            <li>
                <label>
                    <input type="radio" v-model="chosenAnim" name="firstAnim" value="naruto"/>Наруто
                </label>
            </li>
            <li>
                <label>
                    <input type="radio" v-model="chosenAnim" name="firstAnim" value="bleach"/>Блич
                </label>
            </li>
            <li>
                <label>
                    <input type="radio" v-model="chosenAnim" name="firstAnim" value="onePeac"/>Ван пис
                </label>
            </li>
        </ul>
        <button type="sublit" >отправить</button>
    </form>
</template>
<script>
    export default{
        data(){
            return{
            chosenAnim: ''
            }
        },
        methods:{
            submitRadio(){
                console.log(this.chosenAnim);
            }
        }
    }
</script>