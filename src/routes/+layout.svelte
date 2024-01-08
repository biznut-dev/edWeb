<script lang="ts">
	import './mystyles.css';

	import logo from '$lib/images/logo2-nobg.png';
</script>

<!-- svelte-ignore a11y-missing-attribute -->
<!-- svelte-ignore a11y-no-redundant-roles -->
<nav class="navbar has-logo-above" role="navigation" aria-label="main navigation">
	<div class="navbar-brand">
		<a class="navbar-item" href="/">
			<img src={logo} height="58" />
		</a>
		<a
			role="button"
			class="navbar-burger burger"
			aria-label="menu"
			aria-expanded="false"
			data-target="navbarBasicExample"
		>
			<span aria-hidden="true" />
			<span aria-hidden="true" />
			<span aria-hidden="true" />
		</a>
	</div>
	<div id="navbarBasicExample" class="navbar-menu">
		<div class="navbar-start">
			<a class="navbar-item" href="/"> Home </a>
			<a class="navbar-item" href="/resume"> Resume </a>
			<!-- <a class="navbar-item"> Documentation </a>
			<div class="navbar-item has-dropdown is-hoverable">
				<a class="navbar-link"> More </a>
				<div class="navbar-dropdown">
					<a class="navbar-item"> About </a>
					<a class="navbar-item"> Jobs </a>
					<a class="navbar-item"> Contact </a>
					<hr class="navbar-divider" />
					<a class="navbar-item"> Report an issue </a>
				</div>
			</div> -->
		</div>

		<!-- <div class="navbar-end">
            <a href="#" class="navbar-item"><i class="fa fa-search"></i></a>
            <a href="#" class="navbar-item"><i class="fa fa-shopping-bag"></i></a>
        </div> -->
	</div>
</nav>

<slot />

<footer class="footer">
	<div class="content has-text-centered">
		<a href="https://www.linkedin.com/in/ethandav/">LinkedIn</a> <br />
		<a href="https://github.com/biznut-dev">GitHub</a> <br />
		<p>The site was made using Vercel, TypeScript, SvelteKit, and Bulma.</p>
	</div>
</footer>
