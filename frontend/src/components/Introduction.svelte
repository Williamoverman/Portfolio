<script>
    import Card from './Card.svelte';
</script>

<main class="grid grid-cols-12 gap-2.5">
        <Card class="col-span-12 md:col-span-7 bg-(--surface)">
            <div class="absolute inset-0 rounded-2xl pointer-events-none" style="background-image: linear-gradient(rgba(255,255,255,.04) 1px, transparent 1px), linear-gradient(90deg, rgba(255,255,255,.04) 1px, transparent 1px); background-size: 28px 28px;"></div>
            <span class="text-(--muted) text-xs">SOFTWARE ENGINEER - FULLSTACK DEVELOPER - TECH ENTHOUSIAST</span>
            <h2 class="pt-4 font-display text-5xl font-extrabold">WILLIAM<br> <span class="text-3xl text-(--blue)">OVERMAN</span></h2>
        </Card>

        <Card class="col-span-12 md:col-span-5 bg-(--surface)">
            <span class="text-(--muted) text-xs">OVER MIJ</span>
            <p class="pt-2 text-lg font-serif italic">Ik ontwikkel <span class="text-(--purple) font-bold underline">fullstack applicaties</span> met moderne, geavanceerde technologieën. Met focus op schaalbaarheid, performance en een optimale gebruikerservaring.</p>
            <p class="pt-2 font-mono text-xs text-(--muted)">Gebaseerd in Hengelo, NL. Oog voor detail, performance en nette code.</p>
        </Card>

        <Card class="col-span-6 md:col-span-3 bg-(--orange)">
            <span class="text-(--orange-light) text-xs tracking-wide">PROJECTEN</span>
            <h1 class="pt-4 font-display text-5xl font-extrabold text-white">14+</h1>
            <span class="text-(--orange-light) text-xs tracking-wide">publieke repositories</span>
            <span class="absolute -bottom-4 right-1 font-display text-[100px] font-extrabold leading-none pointer-events-none select-none text-white/10">4</span>
        </Card>

        <Card class="col-span-6 md:col-span-3 bg-(--yellow)">
            <span class="text-(--yellow-muted) text-xs tracking-wide">ERVARING</span>
            <h1 class="pt-4 font-display text-5xl font-extrabold text-black">6+</h1>
            <span class="text-(--yellow-muted) text-xs tracking-wide">jaar programmeur</span>
            <span class="absolute -bottom-8 right-1 font-display text-[100px] font-extrabold leading-none pointer-events-none select-none text-black/10">6</span>
        </Card>

        <Card class="col-span-6 md:col-span-2 bg-(--surface)">
            <span class="text-(--muted) text-xs tracking-wide">QUOTE</span>
            <p class="pt-2 text-lg font-serif">“It works on my machine”</p>
        </Card>
        
        <Card class="col-span-6 md:col-span-4 bg-(--surface)">
            <div class="absolute inset-0 rounded-2xl pointer-events-none" style="background: repeating-linear-gradient(-45deg, rgba(255,255,255,.04) 0px, rgba(255,255,255,.04) 1px, transparent 1px, transparent 12px)"></div>
            <span class="text-(--muted) text-xs tracking-wide">EIGENSCHAPPEN</span>
            <div class="grid grid-cols-1 lg:grid-cols-3 gap-2 mt-2">
                <p class="border border-(--border) py-1 rounded-full bg-(--border) text-xs text-center">TEAMSPELER</p>
                <p class="border border-(--border) py-1 rounded-full bg-(--border) text-xs text-center">DOORZETTER</p>
                <p class="border border-(--border) py-1 rounded-full bg-(--border) text-xs text-center">FLEXIBEL</p>
                <p class="border border-(--border) py-1 rounded-full bg-(--border) text-xs text-center">VRIENDELIJK</p>
                <p class="border border-(--border) py-1 rounded-full bg-(--border) text-xs text-center">LEERGIERIG</p>
                <p class="border border-(--border) py-1 rounded-full bg-(--border) text-xs text-center">NIEUWSGIERIG</p>
            </div>
        </Card>
    </main>