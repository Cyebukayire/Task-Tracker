<template>
<button @click="onClick()" :style="{background: color}" class="btn">{{ text }}</button>
</template>

<script>
export default {
    methods: {
    onClick() {
    this.$emit('toggle-add-task')
    },
},
    name: 'Button',
    props: {
        text: String,
        color: String,
    },
}

</script>

