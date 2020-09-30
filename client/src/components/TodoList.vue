<style scoped>
.container {
    align-items: center;
    display: flex;
    flex-direction: column;
}
.add-todo {
    display: flex;
}
.completed {
    text-decoration: line-through;
}
ul {
    text-align: start;
    padding-left: 10;
}
</style>

<template>
    <div class="container">
        <h1>Todo List Vue</h1>
        <div class="add-todo">
            <form @submit="onSubmit">
                <input v-model="newTodo" placeholder="Add Todo" />
                <button @click="onSubmit">Submit</button>
            </form>
        </div>
        <ul>
            <li
                v-for="(todo, index) in todos"
                @click="todo.completed = !todo.completed"
                :key="index"
                :class="{ completed: todo.completed }"
            >
                {{ todo.text }}
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: "TodoList",
    data() {
        return {
            newTodo: "",
            todos: [
                { text: "Take out trash", completed: false },
                { text: "Wash the dishes", completed: false },
                { text: "Do laundry", completed: false },
            ],
        };
    },
    methods: {
        onSubmit(event) {
            if (this.newTodo.trim() !== "") {
                this.todos.push({ text: this.newTodo, completed: false });
            }
            this.newTodo = "";
            event.preventDefault();
        },
    },
};
</script>
