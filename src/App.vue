<template>
	<div id="app">
		<div class="page" v-if="getSpinner">
			<b-spinner
				class="spinner"
				:variant="'primary'"
				:key="'primary'"
			></b-spinner>
		</div>
		<top-header />
		<router-view />
	</div>
</template>

<script>
import TopHeader from './components/TopHeader';
import { mapGetters } from 'vuex';
export default {
	name: 'App',
	components: { 'top-header': TopHeader },
	computed: { ...mapGetters(['getSpinner']) },
};
</script>

<style lang="scss">
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
}

#nav {
	padding: 30px;

	a {
		font-weight: bold;
		color: #2c3e50;

		&.router-link-exact-active {
			color: #42b983;
		}
	}
}

.page {
	position: absolute;
	height: 100%;
	width: 100%;
	z-index: 99;
	background: rgba(0, 0, 0, 0.6);
}

.spinner {
	position: relative;
	top: 50%;
}
</style>
