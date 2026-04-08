<script>
    import Card from './Card.svelte';
    import Chip from './Chip.svelte';
</script>

<main class="grid grid-cols-12 gap-2.5">

    <Card class="col-span-12 md:col-span-5 c-red">
  
        <Chip class="text-xs tracking-[1px] font-medium uppercase text-white/60 mb-3">
            BESCHIKBAAR VOOR
        </Chip>

        <h2 class="t-hero text-white mb-6" style="font-family: 'Fraunces', serif; font-size: 56px; font-weight: 700; line-height: .95; letter-spacing: -2px;">
            Laten we iets<br>
            <span class="italic font-light">moois</span> bouwen.
        </h2>

        <p class="body-text text-sm text-white/75 mt-4 mb-8 leading-relaxed font-sans">
            Freelance, vaste rollen, samenwerking of gewoon een goed gesprek over code.
        </p>

        <div class="mt-8 flex gap-3.5 flex-wrap">
            
            <a href="mailto:jij@portfolio.dev"
            class="inline-block px-7 py-3 rounded-full text-white no-underline transition-all hover:scale-105"
            style="background: #fff; color: #d93b1a; font-family: 'Fraunces', serif; font-weight: 700; font-style: italic; font-size: 14px;">
            Mail mij →
            </a>
            
            <a href="tel:0611658997"
            class="inline-block px-7 py-3 rounded-full no-underline transition-all border border-white/20 hover:scale-105 hover:bg-white/5"
            style="color: rgba(255, 255, 255, .75); font-family: 'Fraunces', serif; font-size: 14px;">
            06 116 589 97
            </a>
        </div>
    </Card>

    <Card class="col-span-12 md:col-span-4 bg-(--beige) overflow-hidden">
        <p class="font-mono text-[9px] tracking-[2.5px] uppercase mb-3 opacity-40 text-black">links</p>
        {#each [
            { label: 'GitHub',        href: 'https://github.com/Williamoverman', arrow: '→' },
            { label: 'LinkedIn',      href: 'https://www.linkedin.com/in/william-overman-3079971b7/',              arrow: '→' },
            { label: 'woverman777@gmail.com',   href: 'mailto:woverman777@gmail.com',        arrow: '↗' },
            { label: 'CV downloaden', href: 'WilliamOvermanCV.pdf',                                 arrow: '↓' },
        ] as link}
            <a href={link.href}
                download={link.label === 'CV downloaden' ? 'William Overman CV.pdf' : undefined}
                target={link.label === 'CV downloaden' ? '_self' : '_blank'}
               class="flex items-center justify-between py-3 border-b border-black/10 last:border-none
                      text-black text-sm font-medium no-underline transition-opacity hover:opacity-50">
                <span>{link.label}</span>
                <span>{link.arrow}</span>
            </a>
        {/each}
    </Card>

    <Card class="col-span-12 md:col-span-3 bg-(--green) overflow-hidden flex flex-col justify-between">
        <p class="font-mono text-[9px] tracking-[2.5px] uppercase" style="color:rgba(0,56,36,.6)">reactietijd</p>
        <div>
            <h2 class="font-display text-6xl font-bold text-black leading-none">&lt;24u</h2>
            <p class="font-mono text-[9px] tracking-[2px] uppercase mt-1" style="color:rgba(0,56,36,.45)">gemiddeld</p>
        </div>
        <span class="absolute -bottom-6 right-1 font-display text-[100px] font-bold leading-none pointer-events-none select-none text-black/5">✓</span>
    </Card>

</main>

<style>
  h2 {
    font-family: var(--font-serif);
  }
  
  a {
    font-family: var(--font-serif);
  }

  :global(.c-red) {
    background-color: #d93b1a !important;
    color: #fff !important;
  }
  
  :global(.card:hover) {
    transform: translateY(-4px) scale(1.012);
  }
</style>