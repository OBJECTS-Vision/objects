<script>
	import Arena from '$lib/components/icons/Arena.svelte';
</script>

<div class="nav">
	<h2>
		<a href="/vision" rel="prefetch"
			>{'Vision'.toUpperCase()}</a
		>
	</h2>
	<h2>
		<a href="/archive" rel="prefetch"
			>{'Archive'.toUpperCase()}<Arena />
		</a>
	</h2>
	<h2>
		<a href="/contact" rel="prefetch">{'Contact'.toUpperCase()}</a>
	</h2>
</div>

<style>
	.nav {
		list-style-type: none;
		text-align: right;
		align-items: center;
	}
</style>
