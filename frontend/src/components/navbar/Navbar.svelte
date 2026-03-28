<script>
import NavItem from './ListItem.svelte';
</script>

<nav class="flex items-center justify-between px-8 py-4 border-b border-white/5 backdrop-blur-xl sticky top-0 z-50">
    <div class="font-extrabold text-md tracking-tight font-display">
        <span class="text-[#ff5e38]">W</span><span class="italic">.OVERMAN</span>
    </div>

    <ul class="flex px-3 py-1 rounded-full bg-white/5 text-white/45 border border-white/15">
        <NavItem href="#over">over</NavItem>
        <NavItem href="#skills">SKILLS</NavItem>
        <NavItem href="#experience">ERVARINGEN</NavItem>
        <NavItem href="#hobbies">HOBBIES</NavItem>
        <NavItem href="#contact">CONTACT</NavItem>
    </ul>
    <div class="flex items-center gap-2 bg-[#00c97a]/10 border border-[#00c97a]/25 rounded-full px-3 py-1.5">
        <span class="relative flex h-[7px] w-[7px]">
        <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-[#00c97a] opacity-50"></span>
        <span class="relative inline-flex h-[7px] w-[7px] rounded-full bg-[#00c97a]"></span>
        </span>
        <span class="text-[11px] tracking-widest uppercase text-[#00c97a]">
            open to work
        </span>
    </div>
</nav>