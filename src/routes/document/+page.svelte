<script lang="ts">
	import { db } from '$lib/firebaseInit';
	import { Document, documentStore } from 'svelte-flame';

	type message = {
		from: string;
		text: string;
	};

	const initialDoc: message = {
		from: 'Marc',
		text: 'World'
	};

	const docStore = documentStore<message>({
		firestore: db,
		ref: 'messages/message'
	});
</script>

<Document ref="messages/message" initial={initialDoc} let:data={message}>
	{#if message !== null}
		<p>Document using component: {message?.from}: {message?.text}</p>
	{/if}
</Document>

{#if $docStore !== null}
<p>Document using store: {$docStore?.from}: {$docStore?.text}</p>
{/if}