<script>
  import { onMount } from 'svelte';
  let visible = false;

  onMount(() => {
    // kleine delay voor smoothness
    setTimeout(() => visible = true, 100);
  });
</script>

<section class="intro" class:visible={visible}>
  <div class="intro-content">
    <h1>Welkom bij Het Ontbijt Atelier</h1>
    <p>Ontdek de kunst van een perfect begin van je dag met onze verse en ambachtelijke ontbijtcreaties.</p>
    <a href="#menu" class="btn-primary">Bekijk ons menu</a>
  </div>
</section>

<style>
.intro {
  color: #222;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 3rem 1rem;
  text-align: center;

  opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.8s ease, transform 0.8s ease;
}

.intro.visible {
  opacity: 1;
  transform: translateY(0);
}

.intro-content {
  max-width: 600px;
}

.intro h1 {
  font-size: 3rem;
  margin-bottom: 1rem;
  font-weight: 700;
  font-family: 'Arial Black', Arial, sans-serif;
}

.intro p {
  font-size: 1.25rem;
  margin-bottom: 2rem;
  line-height: 1.5;
  font-weight: 400;
}

.btn-primary {
  background-color: #f2c94c;
  color: #222;
  padding: 0.75rem 2rem;
  font-weight: 600;
  text-decoration: none;
  border-radius: 30px;
  transition: background-color 0.3s ease;
  display: inline-block;
}

.btn-primary:hover {
  background-color: #d4ac2b;
}

@media (max-width: 768px) {
  .intro h1 {
    font-size: 2.25rem;
  }
  .intro p {
    font-size: 1rem;
  }
}
</style>
