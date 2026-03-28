<script>
    import Card from './Card.svelte';

    const row1 = ['Docker', 'Git', 'AWS', 'Postman', 'Linux', 'Figma']
    const row2 = ['Terraform', 'VS Code', 'IntelliJ', 'Swagger', 'Arduino', 'DevOps']
    const row3 = ['Agile', 'Scrum', 'Shape Up', 'Terraform', 'VS Code', 'IntelliJ']
</script>

<main class="grid grid-cols-12 gap-2.5">
    <Card class="col-span-12 md:col-span-5 bg-(--surface)">
        <span class="text-(--muted) text-xs tracking-[2.5px]">BACKEND</span>

        {#each [
            { name: 'C# / .NET', pct: 85, color: 'var(--purple)' },
            { name: 'Java', pct: 75, color: 'var(--purple)' },
            { name: 'REST API\'s', pct: 80, color: 'var(--blue)'   },
            { name: 'PostgreSQL/MySQL', pct: 80, color: 'var(--blue)'   },
        ] as skill}
            <div class="mb-3">
            <div class="flex justify-between text-[10px] mb-1 opacity-60">
                <span>{skill.name}</span>
                <span>{skill.pct}%</span>
            </div>
            <div class="h-0.75 bg-white/10 rounded-full">
                <div class="h-full rounded-full transition-all duration-700"
                    style="width: {skill.pct}%; background: {skill.color}">
                </div>
            </div>
            </div>
        {/each}
    </Card>

    <Card class="col-span-12 md:col-span-5 bg-(--surface)">
        <span class="text-(--muted) text-xs tracking-[2.5px]">FRONTEND</span>

        {#each [
            { name: 'JavaScript / TypeScript', pct: 80, color: 'var(--yellow)' },
            { name: 'Svelte & Vue.js', pct: 80, color: 'var(--yellow)' },
            { name: 'HTML & CSS', pct: 90, color: 'var(--orange)' },
        ] as skill}
            <div class="mb-3">
            <div class="flex justify-between text-[10px] mb-1 opacity-60">
                <span>{skill.name}</span>
                <span>{skill.pct}%</span>
            </div>
            <div class="h-0.75 bg-white/10 rounded-full">
                <div class="h-full rounded-full transition-all duration-700"
                    style="width: {skill.pct}%; background: {skill.color}">
                </div>
            </div>
            </div>
        {/each}
    </Card>

    <Card class="col-span-12 md:col-span-2 bg-(--green) overflow-hidden">
        <span class="text-(--green-deep) text-xs tracking-[2.5px]">NU AAN HET LEREN</span>
        <h3 class="pt-4 text-black text-4xl font-bold font-display">C++</h3>
    </Card>

    <Card class="col-span-8 bg-(--purple) overflow-hidden">
        <span class="text-(--green-deep) text-xs tracking-[2.5px] uppercase">overige technologieën</span>

        <div class="mt-4 flex flex-col gap-3">
            <div class="overflow-hidden">
                <div class="flex gap-4 whitespace-nowrap animate-marquee">
                    {#each [...row1, ...row1, ...row1] as tech}
                        <span class="font-display text-sm tracking-widest text-(--green-deep) opacity-80">
                            {tech}
                        </span>
                    {/each}
                </div>
            </div>

            <div class="overflow-hidden">
                <div class="flex gap-4 whitespace-nowrap animate-marquee-reverse">
                    {#each [...row2, ...row2, ...row2] as tech}
                        <span class="font-display text-sm tracking-widest text-(--green-deep) opacity-80">
                            {tech}
                        </span>
                    {/each}
                </div>
            </div>

            <div class="overflow-hidden">
                <div class="flex gap-4 whitespace-nowrap animate-marquee">
                    {#each [...row3, ...row3, ...row3] as tech}
                        <span class="font-display text-sm tracking-widest text-(--green-deep) opacity-80">
                            {tech}
                        </span>
                    {/each}
                </div>
            </div>
        </div>
    </Card>

    <Card class="col-span-4 bg-(--surface) overflow-hidden flex justify-center items-center text-center">
        <div>
            <h2 class="text-(--beige) font-display text-1xl font-bold">Mijn projecten</h2>
            <a href="https://github.com/Williamoverman?tab=repositories" class="text-(--blue) font-display">GITHUB -></a>
        </div>
    </Card>
</main>