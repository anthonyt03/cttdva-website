<script>
	import '../app.postcss';

	// Highlight JS
	import hljs from 'highlight.js/lib/core';
	import 'highlight.js/styles/github-dark.css';
	import { storeHighlightJs } from '@skeletonlabs/skeleton';
	import xml from 'highlight.js/lib/languages/xml'; // for HTML
	import css from 'highlight.js/lib/languages/css';
	import javascript from 'highlight.js/lib/languages/javascript';
	import typescript from 'highlight.js/lib/languages/typescript';

	import { AppBar } from '@skeletonlabs/skeleton';
	import { goto } from '$app/navigation';
	import church from '$lib/assets/church.png';
	import logo from '$lib/assets/logo.png';
	import FDLogo from '$lib/assets/FDlogo_v2_90.png';
	import HotdogMenu from './components/HotdogMenu.svelte';

	hljs.registerLanguage('xml', xml); // for HTML
	hljs.registerLanguage('css', css);
	hljs.registerLanguage('javascript', javascript);
	hljs.registerLanguage('typescript', typescript);
	storeHighlightJs.set(hljs);

	// Floating UI for Popups
	import { computePosition, autoUpdate, flip, shift, offset, arrow } from '@floating-ui/dom';
	import { storePopup } from '@skeletonlabs/skeleton';
	storePopup.set({ computePosition, autoUpdate, flip, shift, offset, arrow });

	function handleFaithDirect() {
		window.open('https://membership.faithdirect.net/VA682', '_blank');
	}
</script>

<AppBar
	background="bg-success-900"
	gridColumns="grid-cols-3"
	slotDefault="place-self-center"
	slotTrail="place-content-end"
>
	<svelte:fragment slot="lead">
		<a href="/">
			<img class="w-32" alt="Church Logo" src={church} />
		</a>
	</svelte:fragment>
	<p class="font-sans text-3xl">Holy Martyrs of Vietnam</p>
	<svelte:fragment slot="trail">
		<button type="button" class="btn variant-filled" on:click={handleFaithDirect}>
			<img class="w-32" alt="Faith Direct" src={FDLogo} />
		</button>
	</svelte:fragment>
</AppBar>
<HotdogMenu />
<slot />
<footer class="bg-gray-800 text-white p-4 text-center">
	<p>&copy; {new Date().getFullYear()} Holy Martyrs of Vietnam. All Rights Reserved.</p>
</footer>
