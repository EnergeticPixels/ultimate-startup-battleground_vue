<template>
	<nav class='navbar navbar-default'>
		<div class='navbar-header'>
			<!-- router-link component from vue-router enables seamless client side transition
			between routes without any page reload -->
			<router-link to='/' class='navbar-brand'> The Ultimate Startup Battle Ground</router-link>
		</div>
		<ul class='nav navbar-nav navbar-right'>
			<li>
				<button class='btn btn-danger log' v-show='isLoggedIn()' @click='handleLogout()'>Log Out</button>
				<button class='btn btn-info log' v-show='!isLoggedIn()' @click='handleLogin()'>Log In</button>
			</li>
		</ul>
	</nav>
</template>

<script>
	import { isLoggedIn, login, logout } from '../../utils/auth';

	export default {
		name: 'app-nav',
		methods: {
			handleLogin() {
				login();
			},
			handleLogout() {
				logout();
			},
			isLoggedIn() {
				return isLoggedIn();
			},
		},
	};
</script>

<!-- add 'scoped' attribute to limit CSS to this component only -->
<style scoped>
	.navbar-right {
		margin-right: 0px !important
	}
	.log {
		margin: 5px 10px 0 0;
	}
</script>