<template>
  <div class="app">
    <p>Name:{{ name }}</p>
    <p>Age: {{ age }}</p>
    <button @click="changeName('Zelda')">Change name</button>
    <button @click="changeAge('29')">Change age</button>
  </div>
</template>
<script lang="ts">
  import { defineComponent, reactive, ref } from "vue"

  export default defineComponent({
    name: "App",
    components: {},
    setup() {
      // const state = reactive({
      //   name: "Link",
      //   age: 25 as string | number,
      // })
      const name = ref<string>("Link")
      const age = ref<string | number>(25)

      function changeName(n: string): void {
        name.value = n
        // this.name = name
      }
      function changeAge(a: string | number): void {
        age.value = a
        // this.age = age
      }
      return {
        name,
        age,
        changeName,
        changeAge,
      }
    },
  })
</script>
