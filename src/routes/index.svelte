<script context="module">
	export async function load({ stuff }) {
		const latestPost = stuff.sortedPosts[0];
		const Post = await import(`../posts/${latestPost.slug}.md`);
		return {
			props: {
				Post: Post.default
			}
		};
	}
</script>

<script>
	export let Post;
</script>

<h1>Latest</h1>
<Post />
