<template>
    <div>
        <form @submit="addTodo">
            <input v-model="title" type="text" name="title" placeholder="Add Todo here..." />
            <button type="submit" class="btn">Submit</button>
        </form>
    </div>
</template>

<script>
import { uuid } from 'vue-uuid';

export default {
    name: 'AddTodo',
    data() {
        return {
            title: '',
        }
    },
    methods: {
        addTodo(e) {
            e.preventDefault();
            const newTodo = {
                id: uuid.v1(),
                title: this.title,
                completed: false
            }
            // send up to parent
            this.$emit('add-todo', newTodo); 

            // clear title after submit
            this.title = '';
        }
    }
}
</script>

<style scoped>
    form {
        display: flex;
        width: 100vW;
        justify-content: center;
        align-items: center;
        margin-bottom: 10px;
        margin-top: 10px;
    }
    .btn {
        padding: 10px;
        background: #72a065;
        color: white;
        width: 8vW;
        float: right;
        margin-left: 1vW;
        font-size: 16px;
        cursor: pointer;
    }
    input[type="text"] {
        width: 89vW;
        float: left;
        padding: 10px;
        border: none;
        border-bottom: dashed 2px #72a065;
        font-size: 16px;
    }
    input[type="text"]:focus {
        outline: none;
        border-bottom: dashed 2px #72a065;
    }
</style>