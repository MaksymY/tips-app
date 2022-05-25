<script setup lang="ts">
import AtomButton from "@/components/atoms/AtomButton.vue";
</script>

<template>
    <div class="tipsCalcul">
        <div class="tipsCalcul__section">
            <p class="tipsCalcul__section-description">
                Tips Amount<br><span class="tipsCalcul__section-span">/ persone</span>
            </p>
            <p class="tipsCalcul__section-result">$3.50</p>
        </div>
        <div class="tipsCalcul__section">
            <p class="tipsCalcul__section-description">
                Total<br><span class="tipsCalcul__section-span">/ persone</span>
            </p>
            <p class="tipsCalcul__section-result">$32.79</p>
        </div>
        <AtomButton class="tipsCalcul__button" value="Reset"/>
    </div>
</template>

<style lang="scss">
.tipsCalcul {
    background-color: $Very_dark;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    padding: 25px;
    font-weight: bold;

    &__section {
        display: flex;
        justify-content: space-between;
    }

    &__section-description {
        color: $White;
    }

    &__section-span {
        color: $Dark_grayish;
    }

    &__section-result {
        color: $Primary_cyan;
        font-size: 28px;
    }

    &__button {
        background-color: $Primary_cyan;
        color: $Very_dark;
        font-weight: bold;
    }
}
</style>