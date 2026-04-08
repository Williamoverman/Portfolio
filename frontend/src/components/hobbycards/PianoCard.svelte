<script lang="ts">
    import { onMount } from 'svelte'

    let canvas: HTMLCanvasElement

    onMount(() => {
        const ctx = canvas.getContext('2d')!
        function resize() {
            canvas.width = canvas.offsetWidth
            canvas.height = canvas.offsetHeight
        }
        resize()
        window.addEventListener('resize', resize)

        const stars = Array.from({ length: 55 }, () => ({
            x: Math.random(), y: Math.random(),
            r: 0.5 + Math.random() * 1.5,
            opacity: Math.random() * 0.6,
            t: Math.random() * Math.PI * 2,
            spd: 0.01 + Math.random() * 0.02
        }))

        let raf: number
        function draw() {
            ctx.clearRect(0, 0, canvas.width, canvas.height)
            stars.forEach(s => {
                s.t += s.spd
                const o = s.opacity * (0.5 + 0.5 * Math.sin(s.t))
                ctx.beginPath()
                ctx.arc(s.x * canvas.width, s.y * canvas.height, s.r, 0, Math.PI * 2)
                ctx.fillStyle = `rgba(176,109,255,${o})`
                ctx.fill()
            })
            raf = requestAnimationFrame(draw)
        }
        draw()

        return () => { cancelAnimationFrame(raf); window.removeEventListener('resize', resize) }
    })

    // Piano Web Audio
    const freqs = [261.6, 277.2, 293.7, 311.1, 329.6, 349.2, 370, 392, 415.3, 440, 466.2, 493.9, 523.3, 554.4, 587.3, 622.3, 659.3]
    let audioCtx: AudioContext | null = null
    let activeKeys = new Set<number>()

    function playNote(index: number) {
        try {
            if (!audioCtx) audioCtx = new (window.AudioContext || (window as any).webkitAudioContext)()
            const osc = audioCtx.createOscillator()
            const gain = audioCtx.createGain()
            osc.connect(gain)
            gain.connect(audioCtx.destination)
            osc.frequency.value = freqs[index % freqs.length]
            osc.type = 'triangle'
            gain.gain.setValueAtTime(0, audioCtx.currentTime)
            gain.gain.linearRampToValueAtTime(0.18, audioCtx.currentTime + 0.01)
            gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 1.2)
            osc.start()
            osc.stop(audioCtx.currentTime + 1.2)
        } catch (e) {}
    }

    // Key layout: true = white key, false = black key
    // C D E F G A B C D E F G A B C D E
    const keys = [
        { black: false }, { black: true },
        { black: false }, { black: true },
        { black: false },
        { black: false }, { black: true },
        { black: false }, { black: true },
        { black: false }, { black: true },
        { black: false },
        { black: false }, { black: true },
        { black: false }, { black: true },
        { black: false },
    ]
</script>

<div class="col-span-12 md:col-span-5 rounded-2xl p-6 relative overflow-hidden
            transition-all duration-300 hover:-translate-y-1 hover:scale-[1.01]
            border"
     style="background:linear-gradient(160deg,#090710 0%,#0e0b18 50%,#080610 100%);
            border-color:rgba(176,109,255,.18);">

    <div class="absolute inset-0 rounded-2xl pointer-events-none"
         style="background:radial-gradient(ellipse at 20% 50%,rgba(176,109,255,.1),transparent 60%)"></div>

    <canvas bind:this={canvas}
            class="absolute inset-0 w-full h-full pointer-events-none rounded-2xl opacity-50">
    </canvas>

    <div class="relative z-10">
        <p class="font-mono text-[9px] tracking-[2.5px] uppercase mb-2" style="color:rgba(176,109,255,.5)">
            muziek · instrument · zelf geleerd
        </p>
        <h2 class="font-display text-4xl font-bold tracking-widest" style="color:rgba(240,237,230,.9)">
            PIANO
        </h2>
        <p class="mt-2 text-[11px] leading-relaxed max-w-[220px]" style="color:rgba(200,180,240,.55)">
            Ik hou van klassieke muziek en daarom ben ik begonnen met het leren van piano spelen.
        </p>
        <p class="mt-2 font-mono text-[8px] tracking-[1.5px]" style="color:rgba(176,109,255,.35)">
            SPEEL DE TOETSEN
        </p>
    </div>

    <!-- Piano keys -->
    <div class="relative z-10 mt-4 flex items-end h-[72px]" style="gap:2px">
        {#each keys as key, i}
            {#if key.black}
                <button
                    class="rounded-b-md border-t-0 transition-all duration-75 shrink-0 cursor-pointer"
                    style="width:14px;height:44px;background:linear-gradient(to bottom,#1a1520,#0d0a14);
                           border:1px solid rgba(176,109,255,.08);border-top:none;
                           margin:0 -7px;z-index:3;
                           {activeKeys.has(i) ? 'background:rgba(120,60,220,.8)' : ''}"
                    onmousedown={() => { activeKeys = new Set([...activeKeys, i]); playNote(i) }}
                    onmouseup={() => { activeKeys.delete(i); activeKeys = new Set(activeKeys) }}
                    onmouseleave={() => { activeKeys.delete(i); activeKeys = new Set(activeKeys) }}
                ></button>
            {:else}
                <button
                    class="flex-1 rounded-b-md border-t-0 transition-all duration-75 cursor-pointer"
                    style="height:72px;background:linear-gradient(to bottom,#e8e4f0,#fff);
                           border:1px solid rgba(0,0,0,.12);border-top:none;
                           transform-origin:top;
                           {activeKeys.has(i) ? 'background:linear-gradient(to bottom,rgba(176,109,255,.9),rgba(140,80,255,.7));transform:scaleY(.96)' : ''}"
                    onmousedown={() => { activeKeys = new Set([...activeKeys, i]); playNote(i) }}
                    onmouseup={() => { activeKeys.delete(i); activeKeys = new Set(activeKeys) }}
                    onmouseleave={() => { activeKeys.delete(i); activeKeys = new Set(activeKeys) }}
                ></button>
            {/if}
        {/each}
    </div>
</div>