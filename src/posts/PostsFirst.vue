<template>
<h3>Это первый пост</h3>
<form @submit.prevent="submitText()">
    <h3>
        Введите название аниме которую хотели бы добавить в список
    </h3>
    <input type="text" v-model.trim="inputText"/>
    <h3>Или можете выбрать среди предложанных</h3>
    <label>
        <select v-model="selectAnim">
            <option  value="shriLank">Шри ланк</option>
            <option  value="musasi">Бродяга</option>
            <option  value="drifters">Скитальцы</option>
            <option  value="TakamineSan">Такамине сан</option>
        </select>
    </label>
    <button type="sublit" >отправить</button>
</form>
</template>
<script>
export default{
    data(){
        return{
        inputText: '',
        selectAnim: 'musasi'
        }
    },
    methods:{
        submitText(){
            console.log(this.inputText);
            console.log(this.selectAnim);
        }
    }
}
</script>