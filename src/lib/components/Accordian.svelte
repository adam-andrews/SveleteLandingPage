<script>
	let open = false;
	import Card from '../Card.svelte';
</script>

<div
	class="w-full max-w-md p-2 mx-auto bg-white rounded-2xl shadow-md overflow-hidden md:max-w-2xl"
>
	<div class="flex items-center justify-between p-4">
		<div class="text-lg font-semibold text-gray-700 capitalize dark:text-black">
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
	{#if open}
		<Card />
	{/if}
</div>
