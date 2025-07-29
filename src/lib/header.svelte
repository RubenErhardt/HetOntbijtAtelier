<script>
  import { onMount } from 'svelte';
  let visible = false;

  onMount(() => {
    // Kleine timeout zodat de overgang mooi speelt na mount
    setTimeout(() => {
      visible = true;
    }, 50);
  });
</script>

<header class="header" class:visible={visible}>
  <div class="container">
    <div class="logo">
      <span>Het Ontbijt Atelier</span>
    </div>

    <nav class="nav">
      <a href="/">Home</a>
      <a href="#menu">Menu</a>
      <a href="#over-ons">Over ons</a>
      <a href="#contact">Contact</a>
    </nav>
  </div>
</header>

<style>
.header {
  position: sticky;
  top: 0;
  width: 100%;
  background: white;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.05);
  z-index: 1000;

  /* Start: hidden & slightly omhoog */
  opacity: 0;
  transform: translateY(-10px);
  transition: opacity 0.5s ease, transform 0.5s ease;
}

.header.visible {
  /* Na load: zichtbaar en op plek */
  opacity: 1;
  transform: translateY(0);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 1rem 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-weight: bold;
  font-size: 1.25rem;
  color: #222;
  text-decoration: none;
}

.nav {
  display: flex;
  gap: 1.5rem;
}

.nav a {
  text-decoration: none;
  color: #333;
  font-weight: 500;
  position: relative;
}

.nav a::after {
  content: "";
  position: absolute;
  bottom: -3px;
  left: 0;
  width: 0%;
  height: 2px;
  background: #000;
  transition: width 0.3s ease;
}

.nav a:hover::after {
  width: 100%;
}

@media (max-width: 768px) {
  .nav {
    display: none; /* eventueel vervangen door hamburger menu */
  }
}
</style>
