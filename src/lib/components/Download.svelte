<script>
	function handleClick() {
		const blob = new Blob(['Hello, world!'], {
			type: 'text/plain;charset=utf-8',
		});
		const url = URL.createObjectURL(blob);
		const link = document.createElement('a');
		link.href = url;
		link.download = 'download.txt';
		link.click();
		URL.revokeObjectURL(url);
	}
</script>

<button class="py-2 px-4 bg-blue-500 rounded-lg" on:click={handleClick}
	>Download</button
>
