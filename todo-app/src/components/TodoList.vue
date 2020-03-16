<template>
  <div>
    <ul>
      <li v-for="todo in todos" :key="todo.id">
        <Todo
          v-bind:id="todo.id"
        />
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'
import { createNamespacedHelpers } from 'vuex';
import Todo from './Todo.vue'

@Component({
  components: {
    Todo
  }
})

export default class TodoList extends Vue {
  
}
</script>
