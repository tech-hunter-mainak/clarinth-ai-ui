<script lang="ts">
	import { goto } from '$app/navigation';

	export let text = '';
	export let link = '';
	export let className = '';
	export let icon: string = '';
	export let iconDir: 'left' | 'right' = 'right';
	export let target: '_blank' | '' = '';
    export let type: 'primary' | 'secondary' = 'primary';

	function handleClick() {
		if (!link) return;

		if (target === '_blank') {
			window.open(link, '_blank');
		} else if (link.startsWith('mailto:') || link.startsWith('tel:')) {
			window.open(link);
		} else {
			goto(link);
		}
	}
</script>

<button
	on:click={handleClick}
	class="
		{(type) ? 'bg-button-gradient' : 'stroke-neutral-400'} 
		inline-flex
		w-max
		cursor-pointer
		items-center
		justify-center
		rounded-full
		px-6
		py-3
		text-sm
		font-medium
		text-white
		{iconDir === 'left' ? 'flex-row-reverse' : 'flex-row'}
		{className}
	"
>
	{text}

	{#if icon}
		<img src={icon} alt="" class="ml-2 h-5 w-5 text-white" style="color: white" />
	{/if}
</button>
