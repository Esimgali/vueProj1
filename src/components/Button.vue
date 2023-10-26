<template>
    <button
    @click="$emit('action')"
    >
    <slot></slot>
    </button>
</template>
<script>
export default{
    emit:{
    'action':null
}
}

</script>