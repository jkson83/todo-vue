<template>
    <form @submit.prevent="onsubmit">
        <h2 class="label-wrapper">
        <label for="new-todo-input">What needs to be done? </label>
        </h2>
        <input
        type="text"
        id="new-todo-input"
        name="new-todo"
        autocomplete="off"
        v-model.lazy.trim="label"
        class="input__lg" />
      <button type="submit" class="btn btn__primary btn__lg">Add</button>
    </form>
</template>

<script>
export default {
    methods: {
        onsubmit() {
            if (this.label === "") {
                alert('빈값입니다.');
                return;
            }
            //console.log('Label vlalue:', this.label);
            this.$emit('todo-added', this.label);
        }
    },
    data() {
        return {
            label:"",
        }
    }
}
</script>