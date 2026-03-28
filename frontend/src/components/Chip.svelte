<script lang="ts">
  let { class: cls = '', children } = $props<{ class?: string; children?: any }>()
</script>

<p class="text-[9px] tracking-[2.5px] uppercase opacity-40 mb-2 font-mono {cls}">
  {@render children?.()}
</p>