<script context="module">
	export function preload({ params, query }) {
		return this.fetch(`blog.json`).then(r => r.json()).then(posts => {
			return { posts };
		});
	}
</script>

<script>
  export let posts;

</script>

<style>
  .container {
    width: 100%;
    max-width: 1080px;
    padding-left: 15px;
    padding-right: 15px;
    margin: 2em auto;
  }
</style>

<svelte:head>
	<title>Nguyen Dao - simply blog</title>
</svelte:head>

<div class="container">
  {#each posts as post}
		<!-- we're using the non-standard `rel=prefetch` attribute to
				tell Sapper to load the data for the page as soon as
				the user hovers over the link or taps it, instead of
				waiting for the 'click' event -->
		<a rel='prefetch' href='blog/{post.slug}'>{post.title}</a>
	{/each}
</div>

