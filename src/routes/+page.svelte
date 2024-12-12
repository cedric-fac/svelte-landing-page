<script>
  import { translations } from '$lib/i18n/translations';
  import ScrollToTop from '$lib/components/ScrollToTop.svelte';
  
  let lang = 'fr';
  
  function toggleLanguage() {
    lang = lang === 'fr' ? 'en' : 'fr';
  }
  
  $: t = translations[lang];
</script>

<div class="min-h-screen bg-background">
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

  <main class="container max-w-6xl mx-auto px-4 py-8">
    <section class="text-center mb-16">
      <h2 class="text-4xl font-bold mb-4">{t.subtitle}</h2>
      <p class="text-lg text-muted-foreground">{t.description}</p>
    </section>

    <section class="mb-16">
      <h2 class="text-3xl font-bold mb-8 text-center">{t.packages.title}</h2>
      <div class="grid md:grid-cols-2 gap-8">
        <div class="bg-card p-6 rounded-lg shadow-lg">
          <h3 class="text-2xl font-bold mb-4">{t.packages.basic.title}</h3>
          <ul class="space-y-2 mb-4">
            <li>{t.packages.basic.equipment}</li>
            <li>{t.packages.basic.installation}</li>
          </ul>
          <p class="text-xl font-bold">{t.packages.basic.total}</p>
        </div>
        
        <div class="bg-card p-6 rounded-lg shadow-lg border-primary border-2">
          <h3 class="text-2xl font-bold mb-4">{t.packages.premium.title}</h3>
          <ul class="space-y-2 mb-4">
            <li>{t.packages.premium.equipment}</li>
            <li>{t.packages.premium.installation}</li>
            <li>{t.packages.premium.maintenance}</li>
          </ul>
          <p class="text-xl font-bold">{t.packages.premium.total}</p>
        </div>
      </div>
    </section>

    <section class="mb-16">
      <h2 class="text-3xl font-bold mb-8 text-center">{t.faq.title}</h2>
      <div class="space-y-6">
        <div class="bg-card p-6 rounded-lg">
          <h3 class="text-xl font-bold mb-2">{t.faq.q1}</h3>
          <p>{t.faq.a1}</p>
        </div>
        <div class="bg-card p-6 rounded-lg">
          <h3 class="text-xl font-bold mb-2">{t.faq.q2}</h3>
          <p>{t.faq.a2}</p>
        </div>
      </div>
    </section>

    <section class="text-center">
      <h2 class="text-3xl font-bold mb-8">{t.contact.title}</h2>
      <div class="bg-card p-6 rounded-lg inline-block">
        <p class="mb-4">{t.contact.whatsapp}</p>
        <a
          href="https://chat.whatsapp.com/your-group-link"
          target="_blank"
          rel="noopener noreferrer"
          class="inline-flex items-center gap-2 bg-[#25D366] text-white px-6 py-3 rounded-lg hover:bg-[#22BF5B] transition-colors"
        >
          <svg class="w-6 h-6" viewBox="0 0 24 24" fill="currentColor">
            <path d="M12.031 6.172c-3.181 0-5.767 2.586-5.768 5.766-.001 1.298.38 2.27 1.019 3.287l-.582 2.128 2.182-.573c.978.58 1.911.928 3.145.929 3.178 0 5.767-2.587 5.768-5.766.001-3.187-2.575-5.77-5.764-5.771zm3.392 8.244c-.144.405-.837.774-1.17.824-.299.045-.677.063-1.092-.069-.252-.08-.575-.187-.988-.365-1.739-.751-2.874-2.502-2.961-2.617-.087-.116-.708-.94-.708-1.793s.448-1.273.607-1.446c.159-.173.346-.217.462-.217l.332.006c.106.005.249-.04.39.298.144.347.491 1.2.534 1.287.043.087.072.188.014.304-.058.116-.087.188-.173.289l-.26.304c-.087.086-.177.18-.076.354.101.174.449.741.964 1.201.662.591 1.221.774 1.394.86s.274.072.376-.043c.101-.116.433-.506.549-.68.116-.173.231-.145.39-.087s1.011.477 1.184.564.289.13.332.202c.045.072.045.419-.1.824zm-3.423-14.416c-6.627 0-12 5.373-12 12s5.373 12 12 12 12-5.373 12-12-5.373-12-12-12zm.029 18.88c-1.161 0-2.305-.292-3.318-.844l-3.677.964.984-3.595c-.607-1.052-.927-2.246-.926-3.468.001-3.825 3.113-6.937 6.937-6.937 1.856.001 3.598.723 4.907 2.034 1.31 1.311 2.031 3.054 2.03 4.908-.001 3.825-3.113 6.938-6.937 6.938z"/>
          </svg>
          WhatsApp
        </a>
        <p class="mt-4 text-muted-foreground">{t.contact.delivery}</p>
      </div>
    </section>
  </main>

  <ScrollToTop />
</div>

<style>
  :global(body) {
    background-color: hsl(var(--background));
    color: hsl(var(--foreground));
  }
</style>