<template>
    <ul class="todo-list scroll">
        <TodoItem v-for="todo in todos" :key="todo.id" :todo="todo" />
    </ul>
</template>

<script>
import TodoItem from '@/components/TodoItem.vue'

export default {
    name: 'TodoList',
    components: {
        TodoItem
    },
    props: [
        'todos'
    ]
}
</script>

<style>
    .todo-list {
        position: relative;
        margin: 0;
        padding: 0;
        list-style: none;
        grid-column: 1/-1;
        position: relative;
        z-index: 3;
        max-height: calc(540px - 125px);
        overflow: auto;
    }

    .scroll::-webkit-scrollbar {
        width: 4px;
        height: 4px;
    }

    .scroll::-webkit-scrollbar-thumb {
        border-radius: 10px;
        background-color: var(--orange);
        background-clip: padding-box;
    }

    .scroll::-webkit-scrollbar-track {
        background-color: transparent;
        width: 4px;
        border-radius: 10px;
    }
</style>