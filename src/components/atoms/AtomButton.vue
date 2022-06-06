<script setup lang="ts">
const props = defineProps<{
    value: string | number,
    selected?: boolean,
}>();

</script>

<template>
    <button 
        :class="{'atomButton__selected': props.selected}"
        class="atomButton"
    >{{ props.value }}</button>
</template>

<style lang="scss">
.atomButton {
    background-color: $Very_dark;
    color: $White;
    padding: 20px;
    border: none;
    border-radius: 5px;

    &__selected {
        color: $Very_dark;
        background-color: $Primary_cyan;
    }
}
</style>