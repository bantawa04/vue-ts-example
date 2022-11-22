<template>
  <div class="app">
    <p>Name:{{ state.name }}</p>
    <p>Age: {{ state.age }}</p>
    <button @click="changeName('Zelda')">Change name</button>
    <button @click="changeAge('29')">Change age</button>
  </div>
</template>
<script lang="ts">
  import { defineComponent, reactive } from "vue"

  export default defineComponent({
    name: "App",
    components: {},
    setup() {
      const state = reactive({
        name: "Link",
        age: 25 as string | number,
      })

      function changeName(name: string): void {
        state.name = name
      }
      function changeAge(age: string | number): void {
        state.age = age
      }
      return {
        state,
        changeName,
        changeAge,
      }
    },
  })
</script>
