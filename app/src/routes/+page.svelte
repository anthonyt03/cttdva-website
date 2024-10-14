<script>
	import { AppBar } from '@skeletonlabs/skeleton';
	import { goto } from '$app/navigation';
	import church from '$lib/assets/church.png';
	import logo from '$lib/assets/logo.png';

	function handleFaithDirect() {
		window.open('https://membership.faithdirect.net/VA682', '_blank');
	}
	function handleHome() {
		goto('http://localhost:5173/');
	}
</script>

<title>Holy Martyrs of Vietnam Church</title>
<AppBar
	background="bg-success-900"
	gridColumns="grid-cols-3"
	slotDefault="place-self-center"
	slotTrail="place-content-end"
>
	<svelte:fragment slot="lead">
		<a href='http://localhost:5173/'>
			<img class="w-32" alt="Church Logo" src={logo}/>
		</a>
	</svelte:fragment>
	<p class="font-sans text-3xl">Holy Martyrs of Vietnam</p>
	<svelte:fragment slot="trail">
		<button type="button" class="btn variant-filled" on:click={handleFaithDirect}>
			Faith Direct
		</button>
	</svelte:fragment>
</AppBar>
