<script setup lang="ts">
import AtomButton from "@/components/atoms/AtomButton.vue";
import AtomInput from "@/components/atoms/AtomInput.vue";
</script>

<template>
    <p class="tips__title">Select Tip %</p>
    <div class="tips__buttons">
        <AtomButton value="5%"/>
        <AtomButton value="10%"/>
        <AtomButton value="15%"/>
        <AtomButton value="25%"/>
        <AtomButton value="50%"/>
        <AtomInput class="tips__input" type="text" placeholder="Custom"/>
    </div>
</template>

<style lang="scss">
.tips {
    &__buttons {
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 15px;
    }
    &__title {
        color: $Dark_grayish;
        font-weight: bold;
    }
    &__input {
        &::placeholder {
            color: red !important;
        }
    }
}
</style>