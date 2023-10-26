<template>
    <ul>
        <li v-for="item in news">{{ item.title }} <spn v-if="item.was_read">Этот пост был прочитан</spn></li>
    </ul>
</template>
<script>
export default{
    inject: ['news'] 
}
</script>