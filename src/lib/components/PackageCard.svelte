<script>
  export let title;
  export let items;
  export let total;
  export let isPremium = false;
</script>

<div class="bg-card p-6 rounded-lg shadow-lg {isPremium ? 'border-primary border-2' : ''}">
  <h3 class="text-2xl font-bold mb-4">{title}</h3>
  <ul class="space-y-2 mb-4">
    {#each items as item}
      <li>{item}</li>
    {/each}
  </ul>
  <p class="text-xl font-bold">{total}</p>
</div>