<script lang="ts">
	interface Props {
		children?: import('svelte').Snippet;
		id?: string;
	}

	let { children, id }: Props = $props();
</script>

<p
	{id}
	class="text-[9px] tracking-[3px] uppercase opacity-35 font-mono
	       flex items-center gap-3 mt-12 mb-3
	       after:content-[''] after:flex-1 after:h-px after:bg-white/7"
>
	{@render children?.()}
</p>