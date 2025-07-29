<footer class="footer">
  <div class="container">
    <nav aria-label="Footer navigation" class="footer-nav">
      <ul class="footer-links">
        <li><a href="#menu">Menu</a></li>
        <li><a href="#over-ons">Over ons</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
    <p class="copyright">© 2025 Ontbijt Atelier — Ruben & Ryan</p>
  </div>
</footer>

<style>
.footer {
  background-color: #222; /* iets donkerder voor strak contrast */
  color: #ccc;
  font-family: 'Montserrat', sans-serif;
  font-size: 0.9rem;
  border-top: 1px solid #444; /* subtiele scheidingslijn */
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
}

.footer-nav {
  width: 100%;
}

.footer-links {
  list-style: none;
  display: flex;
  justify-content: center;
  gap: 2.5rem;
  padding: 0;
  margin: 0 0 0.5rem 0;
}

.footer-links a {
  color: #ccc;
  text-decoration: none;
  font-weight: 500;
  letter-spacing: 0.02em;
  transition: color 0.25s ease;
  padding: 0.25rem 0;
  border-bottom: 2px solid transparent;
}

.footer-links a:hover,
.footer-links a:focus {
  color: #fff;
  border-bottom-color: #fff;
  outline: none;
}

.footer-links a:focus-visible {
  outline: 2px solid #fff;
  outline-offset: 3px;
}

.copyright {
  color: #999;
  font-weight: 400;
  font-size: 0.85rem;
  letter-spacing: 0.02em;
}

@media (max-width: 600px) {
  .footer-links {
    flex-direction: column;
    gap: 1rem;
  }
}
</style>
