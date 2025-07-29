<section id="reviews" class="reviews-section" aria-label="Klantenreviews">
  <div class="container">
    <h2 class="section-title">Wat onze klanten zeggen</h2>
    <div class="reviews-grid">
      <blockquote class="review">
        <p>"We bestellen elk weekend voor onze B&B-gasten — altijd vers, netjes verpakt en geliefd bij iedereen!"</p>
        <footer>— Hotelletje aan de Gracht</footer>
      </blockquote>

      <blockquote class="review">
        <p>"Het Luxe pakket was echt een feestje. Perfect voor onze jubileumochtend. Aanrader!"</p>
        <footer>— Simone & Lars</footer>
      </blockquote>

      <blockquote class="review">
        <p>"Eindelijk een ontbijtservice die er niet alleen mooi uitziet, maar ook top smaakt. Onze vaste keuze."</p>
        <footer>— Boutique Hotel Duinzicht</footer>
      </blockquote>
    </div>
  </div>
</section>

<style>
.reviews-section {
  position: relative;
  padding: 6rem 2rem;
  color: #fff;
  background:
    linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)),
    url('/breakfast-with-muffins-coffee-copy-space.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  animation: fadeIn 1.2s ease-out forwards;
}


.reviews-section .section-title {
  font-family: 'Playfair Display', serif;
  font-size: 2.5rem;
  text-align: center;
  margin-bottom: 3rem;
  color: #fff;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.6);
}

.reviews-grid {
  display: grid;
  gap: 2rem;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
}

.review {
  background: rgba(255, 255, 255, 0.1);
  padding: 2rem;
  border-radius: 10px;
  backdrop-filter: blur(6px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  font-style: italic;
  position: relative;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.4);
  color: #fff;
}

.review footer {
  margin-top: 1.5rem;
  font-weight: bold;
  font-style: normal;
  color: #ddd;
}

</style>
