<template>
  <div>
    <input type="checkbox"/>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import { createNamespacedHelpers } from 'vuex'

@Component
export default class Todo extends Vue {
  @Prop() private id!: string;
}
</script>
