<template>
	<b-col>
		<b-card
			:title="name"
			img-src="https://picsum.photos/600/300/?image=25"
			img-alt="Job-info"
			img-top
			tag="article"
			style="max-width: 20rem"
			class="mb-2"
			footer="Card Footer"
		>
			<b-card-text
				>Lorem ipsum dolor sit amet consectetur adipisicing elit. Cupiditate
				natus error quia architecto placeat molestiae?</b-card-text
			>
			<b-button
				v-b-modal="modalID"
				variant="primary"
				v-b-tooltip.hover
				title="Apply here"
				>Apply</b-button
			>
			<b-modal :id="modalID" title="More Information">
				<p class="my-4">Hello modal form lol</p>
			</b-modal>
		</b-card>
	</b-col>
</template>

<script>
export default {
	props: ['name', 'id'],
	computed: {
		modalID() {
			return `modal-${this.id}`;
		},
	},
};
</script>

<style></style>
