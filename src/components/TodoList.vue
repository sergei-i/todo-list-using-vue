<template>
    <div class="list">
        <ul>
            <TodoItem
                    v-for="(todo, i) of todos"
                    v-bind:todo="todo"
                    v-bind:index="i"
                    v-on:remove-todo="removeTodo"
            />
        </ul>
    </div>
</template>

<script>
    import TodoItem from "@/components/TodoItem";

    export default {
        name: "TodoList",
        props: [
            'todos'
        ],
        components: {
            TodoItem
        },
        methods: {
            removeTodo(id) {
                this.$emit('remove-todo', id)
            }
        }
    }
</script>

<style scoped>
    .list {
        max-width: 800px;
        margin: auto;
    }

    ul {
        list-style: none;
        margin: 0;
        padding: 0;
    }
</style>