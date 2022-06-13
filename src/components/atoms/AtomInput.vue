<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps<{
    type: string,
    label?: string,
    placeholder: string,
    icon?: string,
    childClass?: string,
    modelValue?: number
}>();

const path = computed<string>(() => `src/assets/images/icon-${props.icon}.svg`);

</script>

<template>
    <div class="atomInput">
        <label v-if="props.label" class="atomInput__label">{{ props.label }}</label>
        <input
            @input="$emit('update:modelValue', ($event.target as HTMLInputElement).value)"
            :value="props.modelValue === 0 ? null : props.modelValue"
            :style="{'background-image': `url(${path})`}"
            class="atomInput__input"
            :class="childClass"
            :type="props.type" 
            :placeholder="props.placeholder"
        />
    </div>
</template>

<style lang="scss">
.atomInput {
    display: flex;
    flex-direction: column;
    &__label {
        color: $Dark_grayish;
        font-weight: bold;
        margin-bottom: 10px;
    }
    &__input {
        text-align: right; 
        border-radius: 5px;
        border: none;
        padding: 10px;
        color: $Very_dark;
        font-size: 24px;
        font-weight: bold;
        background: no-repeat center left 15px ,$Very_light_grayish;
        height: 100%;
        box-sizing: border-box;
        &::placeholder {
            color: $Light_grayish;
        }
    }
}
</style>