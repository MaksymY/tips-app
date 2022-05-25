<script setup lang="ts">
const props = defineProps<{
    href: string,
    styles?: string,
}>();
</script>

<template>
	<svg>
		<title
			v-if="$slots.default"
		><slot/></title>
		<use
			:href="href.startsWith('#') ? props.href : `#${href}`"
			:class="styles"
		/>
	</svg>
</template>
