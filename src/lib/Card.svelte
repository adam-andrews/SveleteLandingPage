<script>
	import { createEventDispatcher } from 'svelte';
	let open = false;
	export let word;

	const dispatch = createEventDispatcher();

	function handleClick() {
		open = !open;
		dispatch('handleClick', { hello: word });
	}
</script>

<div
	class="p-2 text-gray-800 dark:text-gray-800 md:mx-4 bg-gray-300 rounded-md"
>
	<div class="flex items-center justify-between p-4">
		<div class="text-lg font-semibold text-gray-700 capitalize dark:text-black">
			{word}
		</div>
		<button
			class="w-6 h-6 text-gray-500 dark:text-gray-200"
			on:click={handleClick}
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
		<div class="flex flex-col items-center">
			<input
				class="p-2 m-2 rounded-md focus:none"
				type="text"
				placeholder="Search.."
			/>
			<div class="flex flex-col gap-2">
				Lorem ipsum dolor sit amet, consectetur adipisicing elit. Officiis quas
				porro accusamus similique distinctio inventore consequuntur omnis
				voluptates expedita, architecto vero iste libero corporis numquam sit?
				Reiciendis consectetur rem libero.
			</div>
		</div>
	{/if}
</div>
