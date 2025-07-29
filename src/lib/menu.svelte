<script>
  export let ontbijtjes = [
    {
      naam: 'Basic Ontbijtpakket',
      beschrijving: `Een perfect ontbijt voor een rustige ochtend. 
      Bevat:
– 2 verse croissants met roomboter & aardbeienjam
– Gekookt scharreleitje
– Versgeperste jus d’orange (250ml)
– Mini yoghurt met honing en granola
– Plak bananenbrood
– Thee naar keuze (zakje) of filterkoffie`,
      prijs: '€14,95',
    },
    {
      naam: 'Medium Ontbijtpakket',
      beschrijving: `Voor wie net wat meer wil. 
      Bevat:
– 2 croissants met boter & jam
– Avocado toast met gepocheerd ei
– Yoghurtbeker met granola & fruit
– Smoothie (300ml)
– Muffin of cake
– Notenbrood met roomkaas
– Jus d’orange én koffie of cold brew`,
      prijs: '€21,50',
    },
    {
      naam: 'Luxe Ontbijtpakket',
      beschrijving: `Voor speciale momenten. 
      Bevat:
– Luxe broodassortiment (croissants, pain au chocolat, zuurdesemtoast)
– Hartige selectie: kaas, prosciutto, hummus, truffelmayonaise
– Mini pancakes met maple syrup & bessen
– Vers fruit
– Yoghurt met noten & fruitcompote
– Smoothie en jus d’orange (beide 300ml)
– Mini-cheesecake
– Premium thee + keuze uit cappuccino / latte / cold brew`,
      prijs: '€29,95',
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
  background: rgba(0, 0, 0, 0.65);
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
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
}

.menu-item {
  background: rgba(255, 255, 255, 0.12);
  padding: 2rem;
  border-radius: 12px;
  backdrop-filter: blur(8px);
  border: 1px solid rgba(255, 255, 255, 0.25);
  transition: transform 0.3s ease;
  color: #fff;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.4);
}

.menu-item:hover {
  transform: translateY(-5px);
}

.menu-item h3 {
  font-family: 'Montserrat', sans-serif;
  font-size: 1.6rem;
  margin-bottom: 0.5rem;
}

.menu-item .desc {
  font-size: 1rem;
  line-height: 1.6;
  white-space: pre-line;
  margin-bottom: 1rem;
  letter-spacing: 0.2px;
}

.menu-item .prijs {
  font-weight: 600;
  font-size: 1.2rem;
}

.emoji {
  font-size: 2rem;
  margin-bottom: 0.5rem;
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
    padding: 1.2rem;
  }

  .menu-item h3 {
    font-size: 1.3rem;
  }

  .menu-item .desc {
    font-size: 0.95rem;
  }

  .menu-item .prijs {
    font-size: 1.1rem;
  }
}
</style>
