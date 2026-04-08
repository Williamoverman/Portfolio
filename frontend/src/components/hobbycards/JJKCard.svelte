<script lang="ts">
  import { onMount } from 'svelte'
  import Chip from '../Chip.svelte'

  let canvas: HTMLCanvasElement

  onMount(() => {
    const ctx = canvas.getContext('2d')!
    function resize() {
      canvas.width = canvas.offsetWidth
      canvas.height = canvas.offsetHeight
    }
    resize()
    window.addEventListener('resize', resize)

    const pts = Array.from({ length: 28 }, () => ({
      x: Math.random(), y: Math.random(),
      vx: (Math.random() - 0.5) * 0.35,
      vy: (Math.random() - 0.5) * 0.35,
      r: Math.random() * 2 + 0.5,
      life: Math.random()
    }))

    let raf: number
    function draw() {
      ctx.clearRect(0, 0, canvas.width, canvas.height)
      pts.forEach(p => {
        p.life += 0.004
        if (p.life > 1) { p.life = 0; p.x = Math.random(); p.y = Math.random() }
        const o = 0.5 * Math.sin(p.life * Math.PI)
        p.x += p.vx / canvas.width
        p.y += p.vy / canvas.height
        if (p.x < 0) p.x = 1; if (p.x > 1) p.x = 0
        if (p.y < 0) p.y = 1; if (p.y > 1) p.y = 0
        ctx.beginPath()
        ctx.arc(p.x * canvas.width, p.y * canvas.height, p.r, 0, Math.PI * 2)
        ctx.fillStyle = `rgba(176,109,255,${o})`
        ctx.fill()
      })
      raf = requestAnimationFrame(draw)
    }
    draw()
    return () => { cancelAnimationFrame(raf); window.removeEventListener('resize', resize) }
  })
</script>

<div class="col-span-12 md:col-span-6 rounded-2xl p-6 relative overflow-hidden min-h-[300px] border border-[rgba(176,109,255,0.25)] hover:-translate-y-1 hover:scale-[1.01] transition-all duration-300 hover:shadow-[0_20px_60px_rgba(0,0,0,0.5)]" style="background: linear-gradient(145deg, #09050f 0%, #0e0818 60%, #060310 100%)">
  <div class="absolute inset-0 rounded-2xl pointer-events-none" style="background: radial-gradient(ellipse at 85% 85%, rgba(176,109,255,.2) 0%, transparent 60%), radial-gradient(ellipse at 15% 20%, rgba(100,40,200,.1) 0%, transparent 50%)"></div>

  {#each [0, 1, 2] as i}
    <div class="domain-ring" style="animation-delay: {i * 2}s"></div>
  {/each}

  <svg class="absolute bottom-[-10px] right-[-10px] w-[150px] h-[150px] opacity-[.16] pointer-events-none"
       viewBox="0 0 150 150" fill="none">
    <circle cx="75" cy="75" r="70" stroke="rgba(176,109,255,.8)" stroke-width=".8" stroke-dasharray="6 4"/>
    <circle cx="75" cy="75" r="52" stroke="rgba(176,109,255,.5)" stroke-width=".8" stroke-dasharray="4 6"/>
    <circle cx="75" cy="75" r="34" stroke="rgba(176,109,255,.4)" stroke-width=".8"/>
    <circle cx="75" cy="75" r="8" fill="rgba(176,109,255,.5)"/>
    <line x1="75" y1="5" x2="75" y2="145" stroke="rgba(176,109,255,.25)" stroke-width=".6"/>
    <line x1="5" y1="75" x2="145" y2="75" stroke="rgba(176,109,255,.25)" stroke-width=".6"/>
    <line x1="25" y1="25" x2="125" y2="125" stroke="rgba(176,109,255,.18)" stroke-width=".6"/>
    <line x1="125" y1="25" x2="25" y2="125" stroke="rgba(176,109,255,.18)" stroke-width=".6"/>
    <circle cx="75" cy="5" r="3" fill="rgba(176,109,255,.9)"/>
    <circle cx="145" cy="75" r="3" fill="rgba(176,109,255,.9)"/>
    <circle cx="75" cy="145" r="3" fill="rgba(176,109,255,.9)"/>
    <circle cx="5" cy="75" r="3" fill="rgba(176,109,255,.9)"/>
  </svg>

  <canvas bind:this={canvas} class="absolute inset-0 w-full h-full pointer-events-none rounded-2xl"></canvas>
  
  <div class="relative z-10">
    <Chip class="text-[rgba(176,109,255,0.6)]">FAVORIETE ANIME</Chip>

    <h2 class="font-display text-5xl leading-none tracking-wide mt-1"
        style="color: #c084fc; text-shadow: 0 0 40px rgba(176,109,255,0.5)">
      JUJUTSU<br>KAISEN
    </h2>

    <div class="inline-flex items-center gap-2 mt-3 px-3 py-1.5 rounded-lg bg-[rgba(176,109,255,0.1)] border border-[rgba(176,109,255,0.2)] font-mono text-[10px] tracking-widest text-[rgba(192,132,252,0.8)]">
      <span class="w-[6px] h-[6px] rounded-full bg-[#b06dff] animate-pulse"></span>
      Seizoen 3 · MAPPA · 2026
    </div>

    <p class="mt-3 text-[11px] leading-relaxed max-w-[270px]" style="color: rgba(200,160,255,0.55)">
      Domain expansion. Mijn favoriete show ooit.
      S3 EP 12 = beste episode allertijden.
    </p>

    <blockquote class="mt-3 px-4 py-3 text-[11px] leading-relaxed italic border-l-2 border-[rgba(176,109,255,0.4)] rounded-r-xl bg-[rgba(176,109,255,0.07)]" style="color: rgba(192,132,252,0.85)">
      "Throughout Heaven and Earth, I alone am the honored one."
      <span class="block mt-1 not-italic text-[10px] opacity-45">— Gojo Satoru · Six Eyes</span>
    </blockquote>

    <div class="flex gap-2 flex-wrap mt-3">
      {#each ['MAPPA', '10/10', 'Gege Akutami'] as tag}
        <span class="text-[9px] tracking-widest uppercase px-2 py-1 rounded border border-[rgba(176,109,255,0.25)] text-[rgba(192,132,252,0.6)]">
          {tag}
        </span>
      {/each}
    </div>
  </div>
</div>

<style>
  .domain-ring {
    position: absolute;
    pointer-events: none;
    border-radius: 50%;
    border: 1px solid rgba(176, 109, 255, 0);
    animation: domexp 6s ease-out infinite;
  }
  .domain-ring:nth-child(1) { width: 120px; height: 120px; bottom: -30px; right: -30px; }
  .domain-ring:nth-child(2) { width: 190px; height: 190px; bottom: -60px; right: -60px; }
  .domain-ring:nth-child(3) { width: 260px; height: 260px; bottom: -90px; right: -90px; }

  @keyframes domexp {
    0%   { border-color: rgba(176,109,255,0); transform: scale(0.5); }
    40%  { border-color: rgba(176,109,255,0.35); }
    100% { border-color: rgba(176,109,255,0); transform: scale(1); }
  }
</style>