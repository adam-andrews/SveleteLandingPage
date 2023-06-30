<script>
	import Accordian from '../lib/components/Accordian.svelte';

	const words = {
		parot: 'parejo',
		stop: 'derretir',
		hello: 'hola',
		strong: 'fuerte',
	};
</script>

<div class="flex flex-col items-center bg-red-500">
	<Accordian {words} />
	<div class="my-4">
		<button class="py-2 px-4 bg-blue-500 rounded-lg">Download</button>
	</div>
</div>
