<script setup lang="ts">
import { reactive, computed } from 'vue'
import MoleculeTipsPercentage from "@/components/molecules/MoleculeTipsPercentage.vue";
import MoleculeCalculTips from "@/components/molecules/MoleculeCalculeTips.vue";
import AtomInput from "@/components/atoms/AtomInput.vue";
import AtomIcon from '@/components/atoms/AtomIcon.vue';

interface TipsInfoTypes {
    bill: number
    choicePercentage: number
    numberPeople: number
}

const tipsInfo: TipsInfoTypes = reactive({
    bill: 0,
    choicePercentage: 0,
    numberPeople: 0,
})

function choicePercentage(num: number ) {
    tipsInfo.choicePercentage = num;
}

function reset() {
    tipsInfo.bill = 0;
    tipsInfo.choicePercentage = 0;
    tipsInfo.numberPeople = 0;
}

const calculationTipsPerson = computed<number>(() => {
    const { bill, choicePercentage, numberPeople} = tipsInfo;
    const result = (bill / 100 * choicePercentage) / numberPeople;
    return isNaN(result) ? 0 : +result.toFixed(2);
});

const calculationTotalPerson = computed<number>(() => {
    const { bill, numberPeople} = tipsInfo;
    const result = bill /  numberPeople + calculationTipsPerson.value;
    return isNaN(result) ? 0 : +result.toFixed(2);
})

</script>

<template>
    <section class="tipsContent">
        <AtomIcon class="tipsContent__logo" href="logo" />
        <div class="tipsContent__main">
            <section class="tipsContent__main-left">
                <AtomInput :modelValue="tipsInfo.bill" v-model.number="tipsInfo.bill" label="Bill" type="text" placeholder="0" icon="dollar"/>
                <MoleculeTipsPercentage  @choice-percentage="choicePercentage" />
                <AtomInput :modelValue="tipsInfo.numberPeople" v-model.number="tipsInfo.numberPeople" label="Number of people" type="text" placeholder="0" icon="person"/>
            </section>
            <MoleculeCalculTips
                @reset-tips="reset"
                :tipsPerson="calculationTipsPerson"
                :totalPerson="calculationTotalPerson"
            />
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
    @media (min-width:900px) {
        height: 100vh;
        justify-content: center;
    }

    &__logo {
        width: 100px;
    }

    &__main {
        display: grid;
        gap: 20px;
        background-color: $White;
        border-radius: 10px;
        padding: 30px;
        max-width: 1000px;

        @media (min-width:900px) {
            grid-template-columns: 1fr 1fr;
        }
    }

    &__main-left {
        display: flex;
        flex-direction: column;
        gap: 30px;
    }
}
</style>