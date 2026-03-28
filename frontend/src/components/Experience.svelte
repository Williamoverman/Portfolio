<script>
    import Card from './Card.svelte';
</script>

<main class="grid grid-cols-12 gap-2.5">
  <Card class="col-span-12 md:col-span-5 bg-(--surface)">
    <span class="text-(--muted) text-xs tracking-[2.5px] uppercase">werkervaring</span>
    <div class="mt-3 flex flex-col">

      {#each [
        { year: 'apr. 2024 – feb. 2026', role: 'Junior Software Developer', company: 'COMPAD SOFTWARE · HENGELO', desc: "Backend in C#, frontend met Vue.js & TypeScript, REST API's, Scrum & Shape Up", color: 'var(--orange)', last: false },
        { year: 'nov. 2022 – feb. 2024', role: 'Fietskoerier / Allround',    company: 'FLINK · HENGELO',           desc: 'Multitasking, stressbestendigheid, teamwerk bij piekmomenten',                    color: 'var(--amber)', last: false },
        { year: 'sep. 2020 – jan. 2021', role: 'Allroundmedewerker',          company: 'SUBWAY',                    desc: '',                                                                                color: 'var(--muted)', last: true  },
      ] as item}
        <div class="flex gap-3 {item.last ? '' : 'pb-4'}">
          <div class="flex flex-col items-center pt-1 shrink-0">
            <div class="w-2 h-2 rounded-full shrink-0" style="background: {item.color}"></div>
            {#if !item.last}
              <div class="w-px flex-1 bg-white/7 mt-1.5"></div>
            {/if}
          </div>
          <div>
            <p class="text-[9px] font-mono tracking-widest opacity-50">{item.year}</p>
            <p class="text-sm font-semibold mt-0.5">{item.role}</p>
            <p class="text-[10px] opacity-40 font-mono mt-0.5 tracking-wide">{item.company}</p>
            {#if item.desc}
              <p class="text-[10px] opacity-50 mt-1 leading-relaxed">{item.desc}</p>
            {/if}
          </div>
        </div>
      {/each}

    </div>
  </Card>

  <Card class="col-span-12 md:col-span-4 bg-(--surface)">
    <span class="text-(--muted) text-xs tracking-[2.5px] uppercase">stages</span>
    <div class="mt-3 flex flex-col">

      {#each [
        { year: 'sep. 2023 – feb. 2024', role: 'Software Developer', company: 'COMPAD SOFTWARE', desc: 'Bijgedragen aan opstart van een groot nieuw project in teamverband', color: 'var(--purple)', last: false },
        { year: 'feb. 2022 – jul. 2022',  role: 'Software Developer', company: 'AUTOSOFT',        desc: 'Maatwerk Laravel-websites voor autobedrijven',                       color: 'var(--blue)',   last: true  },
      ] as item}
        <div class="flex gap-3 {item.last ? '' : 'pb-4'}">
          <div class="flex flex-col items-center pt-1 shrink-0">
            <div class="w-2 h-2 rounded-full shrink-0" style="background: {item.color}"></div>
            {#if !item.last}
              <div class="w-px flex-1 bg-white/7 mt-1.5"></div>
            {/if}
          </div>
          <div>
            <p class="text-[9px] font-mono tracking-widest opacity-50">{item.year}</p>
            <p class="text-sm font-semibold mt-0.5">{item.role}</p>
            <p class="text-[10px] opacity-40 font-mono mt-0.5 tracking-wide">{item.company}</p>
            <p class="text-[10px] opacity-50 mt-1 leading-relaxed">{item.desc}</p>
          </div>
        </div>
      {/each}

    </div>
  </Card>

  <Card class="col-span-12 md:col-span-3 bg-(--surface-2)">
    <span class="text-(--muted) text-xs tracking-[2.5px] uppercase">opleiding</span>
    <div class="mt-3 flex flex-col">

      <div class="flex gap-3 pb-4">
        <div class="flex flex-col items-center pt-1 shrink-0">
          <div class="w-2 h-2 rounded-full shrink-0 bg-(--green)"></div>
          <div class="w-px flex-1 bg-white/7 mt-1.5"></div>
        </div>
        <div>
          <p class="text-[9px] font-mono tracking-widest opacity-50">sep. 2024 – heden</p>
          <p class="text-sm font-semibold mt-0.5">HBO-ICT Bachelor</p>
          <p class="text-[10px] opacity-40 font-mono mt-0.5 tracking-wide">HOGESCHOOL SAXION</p>
          <div class="inline-flex items-center gap-2 mt-2 px-3 py-2 rounded-xl bg-(--green)/10 border border-(--green)/20">
            <span class="font-display text-3xl text-(--green)">8.3</span>
            <div>
              <p class="text-[8px] tracking-widest uppercase text-(--green)/60 leading-tight">Propedeuse</p>
              <p class="text-[8px] tracking-widest uppercase text-(--green)/60 leading-tight">nov. 2025</p>
            </div>
          </div>
        </div>
      </div>

      <div class="flex gap-3">
        <div class="flex flex-col items-center pt-1 shrink-0">
          <div class="w-2 h-2 rounded-full shrink-0 bg-white/20"></div>
        </div>
        <div>
          <p class="text-[9px] font-mono tracking-widest opacity-50">sep. 2020 – jul. 2024</p>
          <p class="text-sm font-semibold mt-0.5">MBO Software Developer</p>
          <p class="text-[10px] opacity-40 font-mono mt-0.5 tracking-wide">ROC VAN TWENTE</p>
        </div>
      </div>

    </div>
  </Card>
</main>