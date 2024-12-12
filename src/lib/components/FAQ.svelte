<script>
  export let questions;
</script>

<section class="mb-16">
  <h2 class="text-3xl font-bold mb-8 text-center">{questions.title}</h2>
  <div class="space-y-6">
    <div class="bg-card p-6 rounded-lg">
      <h3 class="text-xl font-bold mb-2">{questions.q1}</h3>
      <p>{questions.a1}</p>
    </div>
    <div class="bg-card p-6 rounded-lg">
      <h3 class="text-xl font-bold mb-2">{questions.q2}</h3>
      <p>{questions.a2}</p>
    </div>
  </div>
</section>