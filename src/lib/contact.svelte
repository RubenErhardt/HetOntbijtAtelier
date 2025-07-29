<section id="contact" class="contact-section" aria-label="Contactformulier">
  <div class="container">
    <h2 class="section-title">Neem contact op</h2>
    <form class="contact-form" on:submit|preventDefault={() => alert('Bericht verzonden!')}>
      <div class="form-group">
        <label for="naam">Naam</label>
        <input type="text" id="naam" name="naam" required />
      </div>

      <div class="form-group">
        <label for="email">E-mailadres</label>
        <input type="email" id="email" name="email" required />
      </div>

      <div class="form-group">
        <label for="bericht">Bericht</label>
        <textarea id="bericht" name="bericht" rows="5" required></textarea>
      </div>

      <button type="submit" class="btn-primary">Verstuur</button>
    </form>
  </div>
</section>

<style>
.contact-section {
  padding: 6rem 2rem;
  background-color: #f9f9f9;
  color: #333;
  animation: fadeIn 1.2s ease-out forwards;
  opacity: 0;
}

.section-title {
  font-family: 'Playfair Display', serif;
  font-size: 2.8rem;
  text-align: center;
  margin-bottom: 2.5rem;
}

.contact-form {
  max-width: 700px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.form-group {
  display: flex;
  flex-direction: column;
}

label {
  font-weight: 600;
  margin-bottom: 0.5rem;
}

input,
textarea {
  font-family: 'Montserrat', sans-serif;
  padding: 0.8rem 1rem;
  border: 1px solid #ccc;
  border-radius: 6px;
  font-size: 1rem;
  transition: border 0.2s ease;
}

input:focus,
textarea:focus {
  border-color: #888;
  outline: none;
}

textarea {
  font-family: 'Montserrat', sans-serif;
  padding: 0.8rem 1rem;
  border: 1px solid #ccc;
  border-radius: 6px;
  font-size: 1rem;
  transition: border 0.2s ease;
  resize: none; /* voorkomt slepen */
}


.btn-primary {
  align-self: flex-start;
  padding: 0.8rem 1.5rem;
  background-color: #333;
  color: #fff;
  border: none;
  border-radius: 6px;
  font-weight: 600;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.btn-primary:hover {
  background-color: #555;
}

@keyframes fadeIn {
  to {
    opacity: 1;
  }
}

@media (max-width: 600px) {
  .section-title {
    font-size: 2.2rem;
  }

  .btn-primary {
    width: 100%;
    text-align: center;
  }
}
</style>
