<template>
  <div class="about-page">

    
    <main class="main-content">
      <div class="about-hero">
        <h1>Acerca de Nosotros</h1>
        <p>Construyendo el futuro de las donaciones 100% descentralizadas</p>
      </div>

      <div class="content-section">
        <!-- Resto del contenido igual -->
        <div class="bento-card">
          <h2>Nuestra Misión</h2>
          <p>
            Crear una plataforma verdaderamente descentralizada donde los creadores 
            reciban donaciones directamente en sus wallets de criptomonedas, 
            sin intermediarios, sin comisiones y con total privacidad.
          </p>
        </div>

        <div class="bento-card">
          <h2>¿Por qué Descentralizado?</h2>
          <div class="benefits-list">
            <div class="benefit-item">
              <div class="benefit-icon">🔒</div>
              <div class="benefit-text">
                <h4>Verdaderamente Descentralizado</h4>
                <p>Sin intermediarios - Las donaciones van directamente a las wallets de los creadores</p>
              </div>
            </div>
            
            <div class="benefit-item">
              <div class="benefit-icon">💰</div>
              <div class="benefit-text">
                <h4>Sin Comisiones de Plataforma</h4>
                <p>100% de las donaciones van directamente para los creadores. Cero comisiones</p>
              </div>
            </div>
            
            <div class="benefit-item">
              <div class="benefit-icon">🔐</div>
              <div class="benefit-text">
                <h4>Privacidad Máxima</h4>
                <p>No se requiere KYC. Mantén tu anonimato y privacidad en todas las transacciones</p>
              </div>
            </div>
            
            <div class="benefit-item">
              <div class="benefit-icon">🌍</div>
              <div class="benefit-text">
                <h4>Acceso Global</h4>
                <p>Funciona en cualquier país sin restricciones geográficas o bancarias</p>
              </div>
            </div>
          </div>
        </div>

        <div class="bento-card">
          <h2>¿Cómo Funciona?</h2>
          <div class="steps-list">
            <div class="step-item">
              <div class="step-number">1</div>
              <div class="step-content">
                <h4>Regístrate como Creador</h4>
                <p>Crea tu perfil y configura tus wallets de criptomonedas (ETH, BTC, USDT)</p>
              </div>
            </div>
            
            <div class="step-item">
              <div class="step-number">2</div>
              <div class="step-content">
                <h4>Comparte tu Perfil</h4>
                <p>Comparte tu enlace y códigos QR con tu audiencia</p>
              </div>
            </div>
            
            <div class="step-item">
              <div class="step-number">3</div>
              <div class="step-content">
                <h4>Recibe Donaciones Directas</h4>
                <p>Las donaciones van directamente a tus wallets sin pasar por la plataforma</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
export default {
  name: 'AboutView'
}
</script>

<style lang="scss" scoped>
.about-page {
  min-height: 100vh;
  background: var(--color-background);
}

.main-content {
  max-width: 800px;
  margin: 0 auto;
  padding: var(--spacing-2xl) var(--spacing-lg);
}

.about-hero {
  text-align: center;
  margin-bottom: var(--spacing-2xl);

  h1 {
    font-size: var(--font-size-4xl);
    font-weight: 700;
    color: var(--color-text);
    margin-bottom: var(--spacing-md);
  }

  p {
    font-size: var(--font-size-xl);
    color: var(--color-text-secondary);
  }
}

.content-section {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-xl);
}

.bento-card {
  background: var(--color-surface);
  border-radius: var(--radius-lg);
  padding: var(--spacing-xl);
  box-shadow: var(--shadow-sm);
  border: 1px solid var(--color-border-light);
}

.benefits-list {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-lg);
  margin-top: var(--spacing-lg);
}

.benefit-item {
  display: flex;
  align-items: flex-start;
  gap: var(--spacing-md);
  padding: var(--spacing-md);
  background: var(--color-background);
  border-radius: var(--radius-md);
  border: 1px solid var(--color-border-light);
}

.benefit-icon {
  font-size: 1.5rem;
  flex-shrink: 0;
}

.benefit-text h4 {
  margin: 0 0 var(--spacing-xs) 0;
  font-size: var(--font-size-base);
  font-weight: 600;
  color: var(--color-text);
}

.benefit-text p {
  margin: 0;
  font-size: var(--font-size-sm);
  color: var(--color-text-secondary);
  line-height: 1.4;
}

.steps-list {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-lg);
  margin-top: var(--spacing-lg);
}

.step-item {
  display: flex;
  align-items: flex-start;
  gap: var(--spacing-md);
  padding: var(--spacing-lg);
  background: var(--color-background);
  border-radius: var(--radius-md);
  border: 1px solid var(--color-border-light);
}

.step-number {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  background: var(--color-primary);
  color: white;
  border-radius: 50%;
  font-weight: 600;
  font-size: var(--font-size-lg);
  flex-shrink: 0;
}

.step-content h4 {
  margin: 0 0 var(--spacing-xs) 0;
  font-size: var(--font-size-base);
  font-weight: 600;
  color: var(--color-text);
}

.step-content p {
  margin: 0;
  font-size: var(--font-size-sm);
  color: var(--color-text-secondary);
  line-height: 1.4;
}

@media (max-width: 768px) {
  .benefit-item,
  .step-item {
    flex-direction: column;
    text-align: center;
  }
  
  .step-number {
    align-self: center;
  }
}
</style>
