<script>
    import Card from '../Card.svelte';

    const songs = [
        { title: "In the Pool", sub: 'kensuke ushio' },
        { title: 'Night theme',    sub: "No, i'm not a human" }
    ]
</script>

<Card class="col-span-12 md:col-span-7 bg-(--surface)">
    <p class="font-mono text-[9px] tracking-[2.5px] uppercase mb-3" style="color:rgba(176,109,255,.4)">
        wat ik speel
    </p>

    {#each songs as song}
        <div class="flex items-center gap-3 mb-2 px-3 py-2 rounded-xl border"
             style="background:rgba(176,109,255,.06);border-color:rgba(176,109,255,.1)">
            <div class="w-7 h-7 rounded-full flex items-center justify-center text-xs shrink-0"
                 style="background:rgba(176,109,255,.15)">
                🎵
            </div>
            <div>
                <p class="text-xs font-semibold leading-tight">{song.title}</p>
                <p class="font-mono text-[9px] opacity-40 mt-0.5 tracking-wide">{song.sub}</p>
            </div>
        </div>
    {/each}
</Card>