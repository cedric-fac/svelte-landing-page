<script>
  import { translations } from '$lib/i18n/translations';

  export let lang;
  export let toggleLanguage;
  $: t = translations[lang];
</script>

<header class="py-6 px-4 bg-primary text-primary-foreground">
  <div class="container max-w-6xl mx-auto flex justify-between items-center">
    <h1 class="text-2xl font-bold">{t.title}</h1>
    <button
      on:click={toggleLanguage}
      class="px-4 py-2 bg-secondary text-secondary-foreground rounded-md hover:bg-secondary/90"
    >
      {lang === 'fr' ? 'English' : 'Français'}
    </button>
  </div>
</header>