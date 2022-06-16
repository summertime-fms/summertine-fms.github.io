<template>
    <li class="todo-list__item" :class="{done: todo.completed}">
            <div class="todo-list__checkbox checkbox" @click="todo.completed = !todo.completed">
                <svg class="checkbox__tick" width="90%" height="100%" viewBox="-40 0 190 100">
                    <path d="M10,50 l30,40 l90,-75" />
                </svg>
            </div>
            <b> {{ todo.title }} </b>
            <p v-if="todo.description"> {{ todo.description }} </p>
    </li>
</template>

<script>
export default {
    props: {
        todo: {
            type: Object,
            required: true
        }
    }
}
</script>

<style>
    .todo-list__item:not(:last-of-type) {
        margin-bottom: 18px;
    }

    .todo-list__item {
        display: grid;
        grid-template-columns: 20px 1fr;
        grid-template-rows: auto auto;
        grid-column-gap: 15px;
        row-gap: 3px;
        align-items: center;
    }

    .todo-list__item.done .checkbox {
        background-color: var(--orange);
    }

    .todo-list__item.done .checkbox path {
        animation: draw var(--trans) forwards 0.155s;
    }

    .todo-list__item.done b {
        color: var(--gray)
    }

    .checkbox {
        width: 100%;
        height: 20px;
        background-color: var(--gray);
        border-radius: 6px;
        grid-row: 1/-1;
        cursor: pointer;
        transition: background-color var(--trans);
    }

    .checkbox__tick path {
        width: 100%;
        height: 100%;
        fill: none;
        stroke: white;
        stroke-width: 20;
        stroke-linecap: round;
        stroke-dasharray: 180;
        stroke-dashoffset: 180;
    }

    .todo-list__item b {
        grid-column: 2/3;
        font-size: 1rem;
        font-weight: 500;
        color: var(--white);
        transition: color var(--trans)
    }

    .todo-list__item p {
        margin: 0;
        grid-column: 2/3;
        font-size: 0.75rem;
        color: var(--gray);
    }
    .done b {
        text-decoration: line-through;
    }

    @keyframes draw {
        to {
            stroke-dashoffset: 0;
        }
}
</style>