<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />

    <div>
      <label for="title">Title: </label>
      <input type="text" v-model="title" placeholder="Title" />
      <label for="body">Body: </label>
      <textarea v-model="body" placeholder="Body"></textarea>
    </div>
    <div>
      <ul v-for="(list, key) in lists" :key="key">
        <li>key: {{ key }} -> {{ list.title }}</li>
      </ul>
      <ul v-for="(list, i) in lists" v-bind:key="i">
        <li>
          id: {{ i }}, title: {{ list.title }}
          <button @click="deleteTodo(i)">Delete</button>
        </li>
      </ul>
    </div>
    <div>
      <input type="submit" value="Add" @click="addTodo" />
    </div>
    <div>
      <pre>
        {{ $data }}
      </pre>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  data: () => ({
    lists: [{ title: "test todo", body: "test body text" }],
    title: "",
    body: ""
  }),
  methods: {
    addTodo: function() {
      if (this.title === "" || this.body === "") return;
      this.lists.push({ title: this.title, body: this.body });
      this.title = "";
      this.body = "";
    },
    deleteTodo: function(i) {
      this.lists.splice(i, 1);
    }
  }
};
</script>
