<template>
    <button class="buttonTambahkan" @click="addTodo">Tambahkan</button>
</template>

<script>
export default {
    methods: {
        addTodo() {
            this.$emit('tambahin');
        }
    }
}
</script>