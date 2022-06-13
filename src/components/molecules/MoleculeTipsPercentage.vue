<script setup lang="ts">
import { ref, watch } from 'vue'
import AtomButton from "@/components/atoms/AtomButton.vue";
import AtomInput from "@/components/atoms/AtomInput.vue";

const percentage = ref<number>(0);
const emit = defineEmits<{ 
    (event: 'choice-percentage', percentage: number): void 
}>()

watch(percentage, (newVal) => {
    emit("choice-percentage", newVal); 
})

</script>

<template>
    <section>
        <p class="tips__title">Select Tip %</p>
        <div class="tips__buttons">
            <AtomButton :selected="percentage === 5" @click="percentage = 5" value="5%"/>
            <AtomButton :selected="percentage === 10" @click="percentage = 10" value="10%"/>
            <AtomButton :selected="percentage === 15" @click="percentage = 15" value="15%"/>
            <AtomButton :selected="percentage === 25" @click="percentage = 25" value="25%"/>
            <AtomButton :selected="percentage === 50" @click="percentage = 50" value="50%"/>
            <AtomInput v-model.number="percentage" :childClass="'tips__input'" type="text" placeholder="Custom"/>
        </div>
    </section>
</template>

<style lang="scss">
.tips {
    &__buttons {
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 15px;

        @media (min-width:900px) {
            grid-template-columns: 1fr 1fr 1fr;
        }
    }
    &__title {
        color: $Dark_grayish;
        font-weight: bold;
        margin: 0 0 10px 0;
    }
    &__input {
        width: 100%;
        &::placeholder {
            color:  $Dark_grayish;
        }
    }
}
</style>