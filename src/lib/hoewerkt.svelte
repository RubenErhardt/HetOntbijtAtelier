<script>
  import { onMount } from 'svelte';
  import gsap from 'gsap';
  import { ScrollTrigger } from 'gsap/ScrollTrigger';

  onMount(() => {
    gsap.registerPlugin(ScrollTrigger);

    const steps = document.querySelectorAll('.step-item');

    steps.forEach((elem, i) => {
      gsap.to(elem, {
        scrollTrigger: {
          trigger: elem,
          start: "top 80%",
          toggleActions: "play none none reverse",
        },
        opacity: 1,
        x: 0,
        duration: 0.6,
        delay: i * 0.2,
        ease: "power2.out"
      });
    });
  });
</script>

<style>
  .how-it-works {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
      Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    max-width: 800px;
    margin: 5rem auto;
    padding: 0 1rem;
    color: #222;
  }

  .how-header {
    text-align: center;
    margin-bottom: 3rem;
  }

  .how-header h2 {
    font-size: 2.8rem;
    font-weight: 700;
    color: #1a3a5a;
    margin-bottom: 0.3rem;
  }

  .how-header p {
    font-size: 1.15rem;
    color: #555;
    max-width: 480px;
    margin: 0 auto;
    line-height: 1.5;
  }

  .steps-list {
    counter-reset: step-counter;
    list-style: none;
    padding: 0;
    margin-bottom: 4rem;
  }

  .step-item {
    position: relative;
    padding-left: 3.5rem;
    margin-bottom: 2.5rem;
    border-left: 3px solid #1a3a5a;

    /* Startpositie animatie */
    opacity: 0;
    transform: translateX(-40px);
  }

  .step-item h3 {
    font-size: 1.6rem;
    font-weight: 600;
    color: #1a3a5a;
    margin-bottom: 0.6rem;
  }

  .step-item p {
    font-size: 1rem;
    color: #444;
    line-height: 1.5;
  }

  .step-item::before {
    counter-increment: step-counter;
    content: counter(step-counter);
    position: absolute;
    left: -1.8rem;
    top: 0;
    font-weight: 700;
    font-size: 2.4rem;
    color: #1a3a5a;
    background: #d0e2f0;
    width: 2.5rem;
    height: 2.5rem;
    line-height: 2.5rem;
    text-align: center;
    border-radius: 50%;
  }

  .b2b-section h3 {
    font-size: 2.2rem;
    font-weight: 700;
    margin-bottom: 1.5rem;
    color: #1a3a5a;
    text-align: center;
  }

  .b2b-list {
    list-style-type: disc;
    list-style-position: inside;
    max-width: 600px;
    margin: 0 auto;
    color: #444;
    font-size: 1.1rem;
    line-height: 1.6;
    padding-left: 0;
  }

  .b2b-list li {
    margin-bottom: 1rem;
  }

  .b2b-list strong {
    color: #1a3a5a;
  }

  @media (max-width: 480px) {
    .how-header h2 {
      font-size: 2rem;
    }

    .step-item {
      padding-left: 2.8rem;
    }

    .step-item::before {
      width: 2rem;
      height: 2rem;
      line-height: 2rem;
      font-size: 1.8rem;
      left: -1.5rem;
    }

    @media (max-width: 768px) {
  .step-item {
    opacity: 1 !important;
    transform: translateX(0) !important;
  }
}

  }
</style>

<section id="hoe-het-werkt" class="how-it-works">
  <div class="container">
    <header class="how-header">
      <h2>Hoe werkt het?</h2>
      <p>
        Ontdek hoe onze ontbijtboxen uw hotel eenvoudig, efficiënt en duurzaam ondersteunen.
      </p>
    </header>

    <ol class="steps-list" aria-label="Stappenplan hoe het werkt">
      <li class="step-item">
        <h3>1. Kies uw formule</h3>
        <p>Abonnement, bulkbestelling of sample-box: een optie die past bij uw behoefte.</p>
      </li>
      <li class="step-item">
        <h3>2. Bestel eenvoudig online</h3>
        <p>Via ons platform bestelt u snel en flexibel, afgestemd op uw bezetting.</p>
      </li>
      <li class="step-item">
        <h3>3. Vers geleverd op locatie</h3>
        <p>Dagelijks vers en op tijd geleverd, klaar voor uw gasten.</p>
      </li>
      <li class="step-item">
        <h3>4. Tevreden gasten</h3>
        <p>Unieke beleving met duurzaam ontbijt en minder verspilling.</p>
      </li>
    </ol>

    <section aria-labelledby="b2b-title" class="b2b-section">
      <h3 id="b2b-title">Onze B2B-aanpak</h3>
      <ul class="b2b-list">
        <li><strong>Flexibele abonnementen</strong> — Levering afgestemd op uw bezettingsgraad, met pauze- en aanpassingsmogelijkheden.</li>
        <li><strong>Bulkbestellingen</strong> — Voordelige tarieven voor grotere bestellingen bij speciale gelegenheden.</li>
        <li><strong>Sample-boxen</strong> — Probeer onze producten eerst zonder verplichtingen.</li>
        <li><strong>Persoonlijke ondersteuning</strong> — Maatwerk en advies op basis van uw wensen.</li>
        <li><strong>Duurzaam partnerschap</strong> — Samen streven we naar minder verspilling en een beter milieu.</li>
      </ul>
    </section>
  </div>
</section>
