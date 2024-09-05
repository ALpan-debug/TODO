<script setup>
import ButtonDelete from './ButtonDelete.vue';

defineProps({todos:{type:Array,Required:true}})

</script>

<template>
    <div>
        <h1>Todo List</h1>
        <div class="grid-conteiner" v-if="todos.length > 0">
            <div class="card" v-for="item of todos" v-bind:keys="item.id">
                <div class="card-content">
                    <h2>{{ item.todo }}</h2>
                    <ButtonDelete @on-click="$emit('remove', item.id)">
                        Delete
                    </ButtonDelete>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>

.grid-conteiner {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 8px;
}

.card {
    background-color: rgb(255, 255, 255);
    padding: 16px 8px;   
    border-radius: 8px;
}

.card-content {
    display: flex;
    justify-content: space-between;
}

h1 {
    margin-bottom: 1rem;
}

h2 {
    font-size: 20px;
}

</style>