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
    </div>
    <div>
      <pre>
        {{ $data }}
      </pre>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  name: "Home",
  data: () => ({
    lists: [{ title: "test todo", body: "test body text" }]
  })
};
</script>
