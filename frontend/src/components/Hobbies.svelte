<script>
    import Card from './Card.svelte';
    import JJKCard from './JJKCard.svelte';
</script>

<main class="grid grid-cols-12 gap-2.5">
    <Card class="col-span-12 md:col-span-6 bg-(--amber)">
        <p class="text-(--yellow-bg) text-xs">Favoriete games</p>
        <span class="font-display text-black text-2xl font-bold">IK GAME.</span><br>
        <span class="font-display text-gray text-2xl font-bold">VEEL.</span>
    </Card>

    <JJKCard />
</main>