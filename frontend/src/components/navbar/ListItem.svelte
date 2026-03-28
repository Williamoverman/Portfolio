<script>
  let { href = "#", children } = $props();
</script>

<li>
  <a
    {href}
    class="block text-[11px] tracking-widest uppercase text-white/45
           px-4 py-1.5 rounded-full transition-all duration-200
           hover:bg-white/8 hover:text-white"
  >
    {@render children()}
  </a>
</li>