<script lang="ts">
  let { class: cls = '', children } = $props()
</script>

<div class="border border-white/7 rounded-2xl p-6 relative overflow-hidden
            transition-all duration-300 hover:-translate-y-1 hover:scale-[1.01] {cls}">
  {@render children?.()}
</div>