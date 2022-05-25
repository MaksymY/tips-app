<script setup lang="ts">
const props = defineProps<{
    value: string | number,
}>();

</script>

<template>
    <button class="AtomButton">{{ props.value }}</button>
</template>

<style lang="scss">
.AtomButton {
    background-color: $Very_dark;
    color: $White;
    padding: 20px;
    border: none;
    border-radius: 5px;
}
</style>