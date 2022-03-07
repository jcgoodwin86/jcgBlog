<script context="module">
	export async function load({ stuff }) {
		const posts = import.meta.globEager('../posts/*.md');
		const postsList = Object.values(posts);
		const postsMeta = postsList.map((post) => {
			return post.metadata;
		});
		const sortedPosts = postsMeta.sort((a, b) => {
			return new Date(b.date) - new Date(a.date);
		});
		return {
			stuff: { sortedPosts },
			props: {
				posts: sortedPosts
			}
		};
	}
</script>

<script>
	import SideHeader from '$lib/components/SideHeader.svelte';
	import PostsMenu from '$lib/components/PostsMenu.svelte';
	import '$lib/styles/style.scss';
	export let posts;
</script>

<SideHeader />

<main>
	<slot />
</main>

<PostsMenu {posts} />
