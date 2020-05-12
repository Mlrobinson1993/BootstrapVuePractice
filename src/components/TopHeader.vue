<template>
	<b-navbar toggleable="lg" type="dark" variant="info">
		<b-navbar-brand href="#">Job Search</b-navbar-brand>

		<b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

		<b-collapse id="nav-collapse" is-nav>
			<b-navbar-nav>
				<b-nav-item to="/">Home</b-nav-item>
			</b-navbar-nav>

			<!-- Right aligned nav items -->
			<b-navbar-nav class="ml-auto">
				<b-nav-form @submit.prevent="handleSearch">
					<b-form-input
						size="sm"
						class="mr-sm-2"
						placeholder="Search"
						v-model="searchText"
					></b-form-input>
					<b-button size="sm" class="my-2 my-sm-0" type="submit"
						>Search</b-button
					>
				</b-nav-form>
			</b-navbar-nav>
		</b-collapse>
	</b-navbar>
</template>

<script>
export default {
	name: 'TopHeader',
	data() {
		return {
			searchText: '',
		};
	},

	methods: {
		handleSearch() {
			this.$store.dispatch('search', { text: this.searchText });
			console.log(this.searchText);
		},
	},
};
</script>

<style lang="scss">
#nav .router-link-exact-active {
	color: white;
}
</style>
