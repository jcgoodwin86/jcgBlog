<script>
	export let posts;
</script>

<div>
	<slot />
	<ul>
		<ui>
			{#each posts as post}
				<li><a href="/{post.slug}">{post.title}</a></li>
				{post.date}
			{/each}
		</ui>
	</ul>
</div>
