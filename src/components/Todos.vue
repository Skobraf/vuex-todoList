<template>
    <div>
        <h3>Todos</h3>
        <div class="todos">
            <div v-for="todo in allTodos" :key="todo.id" class="todo">
                {{ todo.title }}
                <i @click="deleteTodo(todo.id)" class="fas fa-trash-alt"></i>
            </div>
        </div>
    </div>
</template>

<script>
import { mapGetters, mapActions } from 'vuex';

export default {
    name: "Todos",
    methods: {
        ...mapActions(["fetchTodos", "deleteTodo"])
    },
    computed: mapGetters(['allTodos']),
    created() {
        this.fetchTodos();
    }
}
</script>

<style>

</style>
