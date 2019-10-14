<style>
  .wrapper {
    min-height: calc(100vh - 57px);
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column
  }
	.tagline {
		font-size: 24px;
    margin: 0;
    font-family: "Karla", Arial, Helvetica, sans-serif;
  }
</style>

<script>
  import { onMount } from 'svelte';

  onMount(() => {
    if (window.netlifyIdentity) {
      window.netlifyIdentity.on('init', user => {
        if (!user) {
          window.netlifyIdentity.on('login', () => {
            document.location.href = '/admin';
          })
        }
      })
    }
  });
</script>

<svelte:head>
	<title>Nguyen Dao - simply blog</title>
  <script src="https://identity.netlify.com/v1/netlify-identity-widget.js"></script>
</svelte:head>

<div class="wrapper">
  <p class="tagline">I build web user interfaces.</p>
  <a href="mailto: qnguyen.dao@gmail.com">Say hello!</a>
</div>
