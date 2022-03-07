<script context="module">
	export function load({ error, status }) {
		return {
			props: {
				error,
				status
			}
		};
	}
</script>

<script>
	export let error;
	export let status;
</script>

<h1>Something Happen</h1>

<h3>{status}</h3>
<h3>{error.message}</h3>
