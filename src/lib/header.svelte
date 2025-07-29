<script>
  import { onMount } from 'svelte';
  let visible = false;
  let open = false;

  function toggleMenu() {
    open = !open;
  }

  onMount(() => {
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

    <!-- Hamburger knop voor mobiel -->
    <button 
      class="hamburger" 
      aria-label="Menu openen" 
      aria-expanded={open} 
      on:click={toggleMenu}
      aria-controls="primary-navigation"
    >
      <span class="bar"></span>
      <span class="bar"></span>
      <span class="bar"></span>
    </button>

    <nav id="primary-navigation" class="nav" class:open={open}>
      <a href="/" on:click={() => (open = false)}>Home</a>
      <a href="#menu" on:click={() => (open = false)}>Menu</a>
      <a href="#over-ons" on:click={() => (open = false)}>Over ons</a>
      <a href="#contact" on:click={() => (open = false)}>Contact</a>
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
  opacity: 0;
  transform: translateY(-10px);
  transition: opacity 0.5s ease, transform 0.5s ease;
}

.header.visible {
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
  font-weight: bold;
  font-size: 1.25rem;
  color: #222;
  user-select: none;
}

/* Desktop nav */
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

/* Hamburger knop styling */
.hamburger {
  display: none; /* standaard niet zichtbaar */
  flex-direction: column;
  justify-content: space-around;
  width: 28px;
  height: 24px;
  background: transparent;
  border: none;
  cursor: pointer;
  padding: 0;
  z-index: 1100; /* boven menu */
}

.hamburger:focus {
  outline: 2px solid #000;
  outline-offset: 2px;
}

.bar {
  width: 100%;
  height: 3px;
  background-color: #333;
  border-radius: 2px;
  transition: all 0.3s ease;
}

/* Hamburger animatie als menu open is */
.hamburger[aria-expanded="true"] .bar:nth-child(1) {
  transform: rotate(45deg) translate(5px, 5px);
}

.hamburger[aria-expanded="true"] .bar:nth-child(2) {
  opacity: 0;
}

.hamburger[aria-expanded="true"] .bar:nth-child(3) {
  transform: rotate(-45deg) translate(6px, -6px);
}

/* Mobiele versie */
@media (max-width: 768px) {
  .nav {
    position: fixed;
    top: 60px; /* net onder header */
    right: 0;
    background: white;
    width: 200px;
    height: calc(100vh - 60px);
    flex-direction: column;
    padding: 2rem 1rem;
    gap: 1.5rem;
    box-shadow: -2px 0 8px rgba(0,0,0,0.1);
    transform: translateX(100%);
    transition: transform 0.3s ease;
    z-index: 1050;
  }

  .nav.open {
    transform: translateX(0);
  }

  .nav a {
    font-size: 1.2rem;
    color: #222;
  }

  .hamburger {
    display: flex;
  }
}
</style>
