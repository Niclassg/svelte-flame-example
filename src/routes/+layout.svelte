<script lang="en">
	import { db, auth } from './firebaseInit';
	import { SvelteFlame } from "svelte-flame"

</script>

<SvelteFlame {auth} fireStore={db} >
	<a href="/">Home</a>
	<a href="/document">Document</a>
	<a href="/collection">Collection</a>
<slot />
</SvelteFlame>