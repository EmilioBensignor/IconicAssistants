<template>
	<div class="column ga-3">
		<p class="titleSuite text-start">
			Assistants (<span>{{ assistants.length }}</span
			>)
		</p>
		<div class="rowCenter flex-wrap ga-5" v-if="assistants.length > 0">
			<AssistantPreviewComponent
				v-for="(assistant, index) in assistants"
				:key="index"
				:assistant="assistant"
			/>
		</div>
		<p v-else class="text-start">You currently have no assistants</p>
	</div>
</template>

<script>
import AssistantPreviewComponent from "@/suite/components/assistants/AssistantPreviewComponent.vue";

export default {
	name: "AssistantsComponent",
	components: {
		AssistantPreviewComponent,
	},
	props: {
		assistants: {
			type: Array,
			required: true,
		},
	},
};
</script>

<style>
.titleSuite {
	font-size: 1.3rem;
	font-weight: 600;
}
</style>
