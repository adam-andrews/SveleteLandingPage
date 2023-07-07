<script>
	import Accordian from '../lib/components/Accordian.svelte';
	import Download from '../lib/components/Download.svelte';

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
		<Download />
	</div>
</div>
