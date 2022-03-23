<template>
    <button class="buttonTambahkan" @click="tambahkanAddTodo">Tambahkan</button>
</template>

<script>
export default {
    methods: {
        tambahkanAddTodo() {
            this.$emit('tambahin');
        }
    }
}
</script>