<script lang="ts">
	import { Document } from 'svelte-flame';

	type message = {
		from: string;
		text: string;
	};

	const initialDoc: message = {
		from: 'Marc',
		text: 'World'
	};

</script>

<Document ref="messages/message" initial={initialDoc} let:data={message}>
	{#if message !== null}
		<p>Document data: {message?.from}: {message?.text}</p>
	{/if}
</Document>
