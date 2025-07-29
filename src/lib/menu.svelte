
<script>
  export let ontbijtjes = [
    {
      naam: 'Croissant Deluxe',
      beschrijving: 'Verse croissant met roomboter en jam, geserveerd met jus d’orange.',
      prijs: '€4,50',
      emoji: '🥐'
    },
    {
      naam: 'Avocado Toast',
      beschrijving: 'Toast met avocado, limoen, pepervlokken en gepocheerd ei.',
      prijs: '€7,00',
      emoji: '🥑'
    },
    {
      naam: 'Yoghurt Parfait',
      beschrijving: 'Granola met Griekse yoghurt en honing.',
      prijs: '€5,00',
      emoji: '🍓'
    },
    {
      naam: 'Klassiek Ontbijt',
      beschrijving: 'Roerei, bacon, toast en koffie of thee.',
      prijs: '€8,50',
      emoji: '🍳'
    },
    {
      naam: 'Smoothie Bowl',
      beschrijving: 'Banaan, bessen, kokos, chiazaad en havermout.',
      prijs: '€6,50',
      emoji: '🍌'
    },
    {
      naam: 'Pannenkoekjes',
      beschrijving: 'Pancakes met maple syrup en bessen.',
      prijs: '€6,00',
      emoji: '🥞'
    }
  ];
</script>


<section id="menu" class="menu-section" aria-label="Ontbijtmenu">
  <div class="container">
    <h2 class="section-title">Ontbijtmenu</h2>
    <div class="grid">
      {#each ontbijtjes as ontbijt}
        <article class="menu-item" aria-labelledby={ontbijt.naam}>
             <div class="emoji" aria-hidden="true">{ontbijt.emoji}</div>
          <h3 id={ontbijt.naam}>{ontbijt.naam}</h3>
          <p class="desc">{ontbijt.beschrijving}</p>
          <p class="prijs">{ontbijt.prijs}</p>
        </article>
      {/each}
    </div>
  </div>
</section>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600&family=Playfair+Display:wght@600&display=swap');

.menu-section {
  position: relative;
  padding: 6rem 2rem;
  color: #fff;
  animation: fadeIn 1.2s ease-out forwards;
  opacity: 0;
  z-index: 0;
  overflow: hidden;
}

.menu-section::before {
  content: '';
  position: absolute;
  inset: 0;
  background-image: url('/breakfast-with-muffins-coffee-copy-space.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  z-index: -2;
}

.menu-section::after {
  content: '';
  position: absolute;
  inset: 0;
  background: rgba(0, 0, 0, 0.65); /* donkere laag boven de afbeelding */
  z-index: -1;
}

.section-title {
  font-family: 'Playfair Display', serif;
  font-size: 3rem;
  text-align: center;
  margin-bottom: 3rem;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.6);
}

.grid {
  display: grid;
  gap: 2rem;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
}

.menu-item {
  background: rgba(255, 255, 255, 0.1);
  padding: 1.5rem;
  border-radius: 10px;
  backdrop-filter: blur(6px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  transition: transform 0.3s ease;
  color: #fff;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.4);
}

.menu-item:hover {
  transform: translateY(-4px);
}

.menu-item h3 {
  font-family: 'Montserrat', sans-serif;
  font-size: 1.5rem;
  margin-bottom: 0.5rem;
}

.menu-item .desc {
  font-size: 1rem;
  margin-bottom: 0.5rem;
}

.menu-item .prijs {
  font-weight: 600;
  font-size: 1.1rem;
}

/* Fade-in animatie */
@keyframes fadeIn {
  to {
    opacity: 1;
  }
}

@media (max-width: 600px) {
  .section-title {
    font-size: 2.2rem;
  }

  .menu-item {
    padding: 1rem;
  }
}
</style>
