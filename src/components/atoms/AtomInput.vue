<script setup lang="ts">
import { computed } from 'vue'
const props = defineProps<{
    type: string,
    label?: string,
    placeholder: string,
    icon: string
}>();
const path = computed<string>(() => `src/assets/images/icon-${props.icon}.svg`)

</script>

<template>
    <div class="atomInput">
        <label v-if="props.label" class="atomInput__label">{{ props.label }}</label>
        <input
            :style="{'background-image': `url(${path})`}"
            class="atomInput__input"
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
    }
    &__input {
        text-align: right; 
        border-radius: 5px;
        border: none;
        padding: 10px;
        color: $Very_dark;
        background: no-repeat center left 15px ,$Very_light_grayish;
        &::placeholder {
            color: $Light_grayish;
        }
    }
}
</style>