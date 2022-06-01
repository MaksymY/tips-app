<script setup lang="ts">
import MoleculeTipsPercentage from "@/components/molecules/MoleculeTipsPercentage.vue";
import MoleculeCalculTips from "@/components/molecules/MoleculeCalculeTips.vue";
import AtomInput from "@/components/atoms/AtomInput.vue";
import AtomIcon from '@/components/atoms/AtomIcon.vue';
</script>

<template>
    <section class="tipsContent">
        <AtomIcon class="tipsContent__logo" href="logo" />
        <div class="tipsContent__main">
            <AtomInput label="Bill" type="text" placeholder="0" icon="dollar"/>
            <MoleculeTipsPercentage />
            <AtomInput label="Number of people" type="text" placeholder="0" icon="person"/>
            <MoleculeCalculTips />
        </div>
    </section>
</template>

<style lang="scss">
.tipsContent {
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    background-color: $Light_grayish;
    align-items: center;

    &__logo {
        width: 100px;
    }

    &__main {
        display: grid;
        gap: 20px;
        background-color: $White;
        border-radius: 10px;
        padding: 30px;
    }
}
</style>