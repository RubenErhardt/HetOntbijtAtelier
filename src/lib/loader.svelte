<script>
  export let loading = true;
</script>

<div class="loader-screen" class:visible={loading}>
  <h1 class="brand-title">
    <span>H</span><span>e</span><span>t</span>&nbsp;
    <span>O</span><span>n</span><span>t</span><span>b</span><span>i</span><span>j</span><span>t</span>&nbsp;
    <span>A</span><span>t</span><span>e</span><span>l</span><span>i</span><span>e</span><span>r</span>
  </h1>
</div>

<style>
.loader-screen {
  position: fixed;
  inset: 0;
  background-color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 9999;
  opacity: 1;
  visibility: visible;
  transition: opacity 1s ease, visibility 1s ease;
}

.loader-screen:not(.visible) {
  opacity: 0;
  visibility: hidden;
  pointer-events: none;
}

.brand-title {
  display: flex;
  flex-wrap: wrap;
  gap: 3px;
  padding: 20px;
  font-size: 4rem;
  font-family: Arial, sans-serif;
  color: #222;
  justify-content: center;
  align-items: center;
}

.brand-title span {
  opacity: 0;
  transform: translateY(10px);
  animation: fadeInUp 0.8s forwards;
}

@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Letter animatie delays */
.brand-title span:nth-child(1) { animation-delay: 0.05s; }
.brand-title span:nth-child(2) { animation-delay: 0.1s; }
.brand-title span:nth-child(3) { animation-delay: 0.15s; }
.brand-title span:nth-child(4) { animation-delay: 0.2s; }
.brand-title span:nth-child(5) { animation-delay: 0.25s; }
.brand-title span:nth-child(6) { animation-delay: 0.3s; }
.brand-title span:nth-child(7) { animation-delay: 0.35s; }
.brand-title span:nth-child(8) { animation-delay: 0.4s; }
.brand-title span:nth-child(9) { animation-delay: 0.45s; }
.brand-title span:nth-child(10) { animation-delay: 0.5s; }
.brand-title span:nth-child(11) { animation-delay: 0.55s; }
.brand-title span:nth-child(12) { animation-delay: 0.6s; }
.brand-title span:nth-child(13) { animation-delay: 0.65s; }
.brand-title span:nth-child(14) { animation-delay: 0.7s; }
.brand-title span:nth-child(15) { animation-delay: 0.75s; }
.brand-title span:nth-child(16) { animation-delay: 0.8s; }
.brand-title span:nth-child(17) { animation-delay: 0.85s; }

@media (max-width: 768px) {
  .brand-title {
    font-size: 3rem;
    gap: 2px;
  }
}

@media (max-width: 480px) {
  .brand-title {
    font-size: 2rem;
    text-align: center;
  }
}
</style>

