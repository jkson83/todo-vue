<template>
    <form @submit.prevent="onsubmit">
        <label for="new-todo-input">What needs to be done? </label>
        <input
        type="text"
        id="new-todo-input"
        name="new-todo"
        autocomplete="off"
        v-model="label" />
      <button type="submit">Add</button>
    </form>
</template>

<script>
export default {
    methods: {
        onsubmit() {
            console.log('Label vlalue:', this.label);
        }
    },
    data() {
        return {
            label:"",
        }
    }
}
</script>