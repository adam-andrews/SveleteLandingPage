<script>
	let open = false;
	import Card from '../Card.svelte';
	export let word;

	let showCards = true; // Reactive variable to control the view

	function handleClickEvent(event) {
		console.log('handleClickEvent', event.detail);
		console.log('handleClickEvent', event.detail.hello);
		word = event.detail.hello;
		showCards = !showCards; // Switch between cards and other content
	}

	function backButton() {
		showCards = !showCards;
	}

	const wordsTemplate = {
		parot: 'parejo',
		stop: 'derretir',
		hello: 'hola',
		strong: 'fuerte',
		parot1: 'parejo',
		stop1: 'derretir',
		hello1: 'hola',
		strong1: 'fuerte',
		parot2: 'parejo',
		stop2: 'derretir',
		hello2: 'hola',
		strong2: 'fuerte',
		parot3: 'parejo',
		stop3: 'derretir',
		hello3: 'hola',
		strong3: 'fuerte',
	};
</script>

<div>
	<div
		class="w-full max-w-md p-2 mx-auto bg-white rounded-2xl shadow-md overflow-hidden md:max-w-2xl mb-4"
	>
		<div class="flex items-center justify-between p-4">
			<div
				class="text-lg font-semibold text-gray-700 capitalize dark:text-black"
			>
				Accordion
			</div>
			<button
				class="w-6 h-6 text-gray-500 dark:text-gray-200"
				on:click={() => (open = !open)}
			>
				{#if open}
					<svg
						xmlns="http://www.w3.org/2000/svg"
						fill="none"
						viewBox="0 0 24 24"
						stroke="currentColor"
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M19 9l-7 7-7-7"
						/>
					</svg>
				{:else}
					<svg
						xmlns="http://www.w3.org/2000/svg"
						fill="none"
						viewBox="0 0 24 24"
						stroke="currentColor"
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M5 15l7-7 7 7"
						/>
					</svg>
				{/if}
			</button>
		</div>
	</div>

	{#if open}
		<div class="grid grid-cols-4 gap-2 bg-blue-500 p-8">
			{#if showCards}
				{#each Object.entries(wordsTemplate) as [key, word]}
					<Card on:handleClick={handleClickEvent} {word} />
				{/each}
			{:else}
				<button on:click={backButton}> Hello</button>
				<div>{word}</div>
			{/if}
		</div>
	{/if}
</div>
