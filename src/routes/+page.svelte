<script>
  import { translations } from '$lib/i18n/translations';
  import Header from '$lib/components/Header.svelte';
  import PackageCard from '$lib/components/PackageCard.svelte';
  import FAQ from '$lib/components/FAQ.svelte';
  import Contact from '$lib/components/Contact.svelte';
  import ScrollToTop from '$lib/components/ScrollToTop.svelte';
  
  let lang = 'fr';
  
  function toggleLanguage() {
    lang = lang === 'fr' ? 'en' : 'fr';
  }
  
  $: t = translations[lang];
</script>

<div class="min-h-screen bg-background">
  <Header {lang} {toggleLanguage} />

  <main class="container max-w-6xl mx-auto px-4 py-8">
    <section class="text-center mb-16">
      <h2 class="text-4xl font-bold mb-4">{t.subtitle}</h2>
      <p class="text-lg text-muted-foreground">{t.description}</p>
    </section>

    <section class="mb-16">
      <h2 class="text-3xl font-bold mb-8 text-center">{t.packages.title}</h2>
      <div class="grid md:grid-cols-2 gap-8">
        <PackageCard
          title={t.packages.basic.title}
          items={[t.packages.basic.equipment, t.packages.basic.installation]}
          total={t.packages.basic.total}
        />
        
        <PackageCard
          title={t.packages.premium.title}
          items={[t.packages.premium.equipment, t.packages.premium.installation, t.packages.premium.maintenance]}
          total={t.packages.premium.total}
          isPremium={true}
        />
      </div>
    </section>

    <FAQ questions={t.faq} />
    <Contact contact={t.contact} />
  </main>

  <ScrollToTop />
</div>

<style>
  :global(body) {
    background-color: hsl(var(--background));
    color: hsl(var(--foreground));
  }
</style>