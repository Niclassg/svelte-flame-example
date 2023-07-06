<script lang="ts">
	import { Collection } from 'svelte-flame';

	type message = {
		from: string;
		text: string;
	};
	const initialCol: message[] = [];
</script>

<Collection ref="messages" initial={initialCol} let:data={messages}>
	{#if messages !== null}
		<ul>
			{#each messages as message}
				<li>{message.from}: {message.text}</li>
			{/each}
		</ul>
	{/if}
</Collection>
