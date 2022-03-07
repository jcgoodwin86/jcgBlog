<script context="module">
	export async function load({ params }) {
		const Post = await import(`../posts/${params.slug}.md`);
		return {
			// Data passed into svetle component
			props: {
				Post: Post.default
			}
		};
	}
</script>

<script>
	export let Post;
</script>

<svelte:component this={Post} />
