<template>
<button @click="onClick()" :style="{background: color}" class="btn">{{ text }}</button>
</template>

<script>
export default {
    methods: {
    onClick() {
    console.log("Button Clicked");
    }
},
    name: 'Button',
    props: {
        text: String,
        color: String,
    },
}

</script>

