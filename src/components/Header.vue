<template>
    <header>
        <h2>{{ title }}</h2>
        <Button v-show="homePage" @btn-click="$emit('btn-click')" :text="showAddTask ? 'Close': 'Add Task'" :color=" showAddTask ? 'red' : 'green'" />
    </header>
</template>

<script>
import Button from './Button'

export default {
    name: 'Header',
    props: {
        title: String,
        showAddTask: Boolean
    },
    components: {
        Button
    },
    computed: {
        homePage() {
            if(this.$route.path === '/'){
                return true
            }else{
                return false
            }
        }
    }
}
</script>

<style scoped>
header {
    display: flex;
    justify-content: space-between;
    align-items: cetner;
    margin-bottom: 20px;
}
</style>