<script>
	import NavItem from './ListItem.svelte';

	let open = $state(false);

	const links = [
		{ href: '#over', label: 'over' },
		{ href: '#skills', label: 'SKILLS' },
		{ href: '#experience', label: 'ERVARINGEN' },
		{ href: '#hobbies', label: 'HOBBIES' },
		{ href: '#contact', label: 'CONTACT' }
	];
</script>

<nav class="flex flex-col border-b border-white/5 backdrop-blur-xl sticky top-0 z-50">
	<div class="flex items-center justify-between px-8 py-4">
		<div class="font-extrabold text-md tracking-tight font-display">
			<span class="text-[#ff5e38]">W</span><span class="italic">.OVERMAN</span>
		</div>

		<ul class="hidden md:flex px-3 py-1 rounded-full bg-white/5 text-white/45 border border-white/15">
			{#each links as link}
				<NavItem href={link.href}>{link.label}</NavItem>
			{/each}
		</ul>

		<div class="flex items-center gap-3">
			<div class="flex items-center gap-2 bg-[#00c97a]/10 border border-[#00c97a]/25 rounded-full px-3 py-1.5">
				<span class="relative flex h-[7px] w-[7px]">
					<span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-[#00c97a] opacity-50"></span>
					<span class="relative inline-flex h-[7px] w-[7px] rounded-full bg-[#00c97a]"></span>
				</span>
				<span class="text-[11px] tracking-widest uppercase text-[#00c97a]">
					open to work
				</span>
			</div>

			<button
				class="md:hidden w-10 h-10 flex items-center justify-center text-white/70 hover:text-white transition-colors"
				onclick={() => (open = !open)}
			>
				{#if open}
					<svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
						<path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
					</svg>
				{:else}
					<svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
						<path stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16M4 18h16" />
					</svg>
				{/if}
			</button>
		</div>
	</div>

	{#if open}
		<div class="md:hidden px-8 pb-8 bg-black/95 border-t border-white/10">
			<ul class="flex flex-col">
				{#each links as link}
					<li>
						<a
							href={link.href}
							onclick={() => (open = false)}
							class="block py-5 text-[13px] tracking-[1px] uppercase text-white/75 hover:text-white border-b border-white/10 last:border-none transition-colors"
						>
							{link.label}
						</a>
					</li>
				{/each}
			</ul>
		</div>
	{/if}
</nav>