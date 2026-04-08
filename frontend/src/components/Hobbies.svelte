<script>
    import Card from './Card.svelte';
    import JJKCard from './hobbycards/JJKCard.svelte';
    import PianoCard from './hobbycards/PianoCard.svelte';
    import Setlist from './hobbycards/SetlistCard.svelte';
</script>

<main class="grid grid-cols-12 gap-2.5">

    <Card class="col-span-12 md:col-span-6 bg-(--amber) overflow-hidden">
        <p class="text-(--yellow-bg) text-xs tracking-[2.5px] uppercase">Gaming · actief gespeeld</p>

        <div class="flex items-start justify-between">
            <div>
                <span class="font-display text-black text-4xl font-bold leading-none">IK GAME.</span><br>
                <span class="font-display text-black/20 text-4xl font-bold leading-none">VEEL.</span>
            </div>
            <svg class="w-7 h-7 opacity-20 mt-1 shrink-0" viewBox="0 0 28 28" fill="none">
                <circle cx="14" cy="14" r="13" stroke="black" stroke-width=".8"/>
                <circle cx="14" cy="14" r="3" stroke="black" stroke-width=".8"/>
                <line x1="14" y1="0" x2="14" y2="8" stroke="black" stroke-width=".8"/>
                <line x1="14" y1="20" x2="14" y2="28" stroke="black" stroke-width=".8"/>
                <line x1="0" y1="14" x2="8" y2="14" stroke="black" stroke-width=".8"/>
                <line x1="20" y1="14" x2="28" y2="14" stroke="black" stroke-width=".8"/>
            </svg>
        </div>

        <p class="font-mono text-[9px] tracking-[2px] uppercase text-black/30 mt-2">[ 3 actieve games · hundreds of hours lost ]</p>

        <div class="flex flex-col gap-2 mt-3">
            <div class="flex items-center gap-3 px-3 py-2 rounded-xl border" style="background:rgba(0,0,0,0.06);border-color:rgba(0,0,0,0.12)">
                <div class="flex-1 min-w-0">
                    <p class="text-xs font-semibold text-black">The Outlast Trials</p>
                    <p class="font-mono text-[8px] text-black/40 mt-0.5 tracking-wide">SURVIVAL HORROR · CO-OP</p>
                </div>
            </div>

            <div class="flex items-center gap-3 px-3 py-2 rounded-xl border" style="background:rgba(0,0,0,0.06);border-color:rgba(0,0,0,0.12)">
                <div class="flex-1 min-w-0">
                    <p class="text-xs font-semibold text-black">Arc Raiders</p>
                    <p class="font-mono text-[8px] text-black/40 mt-0.5 tracking-wide">EXTRACTION · PVPVE</p>
                </div>
            </div>

            <div class="flex items-center gap-3 px-3 py-2 rounded-xl border" style="background:rgba(0,0,0,0.06);border-color:rgba(0,0,0,0.12)">
                <div class="flex-1 min-w-0">
                    <p class="text-xs font-semibold text-black">Team Fortress 2</p>
                    <p class="font-mono text-[8px] text-black/40 mt-0.5 tracking-wide">FPS · SCOUT MAIN</p>
                </div>
            </div>
        </div>
    </Card>

    <JJKCard />

    <PianoCard />

    <Setlist />

</main>