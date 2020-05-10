 <template>
    <div>
        <div v-for="data in todosData" v-bind:key="data.id">
            <TodoItem v-bind:propsTodo="data" v-on:del-todo="$emit('del-todo', data.id)" />
        </div>
    </div>
 </template>

<script>
import TodoItem from './TodoItem.vue';

export default {
  name: 'Todos',
  props: ['todosData'],
  components: {
      TodoItem
  } 
}
</script>