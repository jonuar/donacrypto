<template>
  <div class="home-page">
    <nav class="navbar" v-if="!authStore.estaAutenticado">
      <div class="nav-container">
        <div class="nav-brand">
          <span class="brand-icon">💜</span>
          <span class="brand-text">DonaCrypto</span>
        </div>
        <div class="nav-actions">
          <router-link to="/login" class="btn btn-ghost">
            Iniciar sesión
          </router-link>
          <router-link to="/register" class="btn btn-primary">
            Registrarse
          </router-link>
        </div>
      </div>
    </nav>

    <main class="main-content">
      <div class="hero-section">
        <div class="hero-content">
          <h1 class="hero-title">
            El futuro de las donaciones
            <span class="text-primary">descentralizadas</span>
          </h1>
          <p class="hero-subtitle">
            Conecta directamente con tus creadores favoritos y apóyalos 
            de manera transparente y segura.
          </p>
          <div class="hero-actions">
            <router-link to="/register" class="btn btn-primary btn-lg">
              Comenzar Ahora
            </router-link>
            <router-link to="/about" class="btn btn-secondary btn-lg">
              Saber Más
            </router-link>
          </div>
        </div>
        <div class="hero-visual">
          <div class="hero-card">
            <div class="card-header">
              <div class="creator-avatar">🎨</div>
              <div class="creator-info">
                <h4>María López</h4>
                <p>@maria_art</p>
              </div>
            </div>
            <div class="card-content">
              <p>¡Gracias por apoyar mi arte!</p>
              <div class="donation-amount">
                <span class="amount">0.5 ETH</span>
                <span class="label">recibido</span>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="features-section">
        <h2 class="section-title">¿Por qué elegirnos?</h2>
        <div class="features-grid">
          <div class="feature-card bento-card">
            <div class="feature-icon">🔒</div>
            <h3>Verdaderamente Descentralizado</h3>
            <p>Sin intermediarios - Las donaciones van directamente a las wallets de los creadores.</p>
          </div>
          <div class="feature-card bento-card">
            <div class="feature-icon">💰</div>
            <h3>Sin Comisiones de Plataforma</h3>
            <p>100% de las donaciones van directamente para los creadores. Cero comisiones.</p>
          </div>
          <div class="feature-card bento-card">
            <div class="feature-icon">🔐</div>
            <h3>Privacidad Máxima</h3>
            <p>No se requiere KYC. Mantén tu anonimato y privacidad en todas las donaciones.</p>
          </div>
          <div class="feature-card bento-card">
            <div class="feature-icon">🌍</div>
            <h3>Acceso Global</h3>
            <p>Funciona en cualquier país sin restricciones geográficas o bancarias.</p>
          </div>
        </div>
      </div>
    </main>

    <footer class="footer">
      <p>&copy; 2025 DonaCrypto. Todos los derechos reservados.</p>
    </footer>
  </div>
</template>

<script>
import { useRouter } from 'vue-router'
import { useToast } from 'vue-toastification'
import { useAuthStore } from '@/stores/auth'

export default {
  name: 'HomeView',
  setup() {
    const router = useRouter()
    const toast = useToast()
    const authStore = useAuthStore()

    const handleLogout = () => {
      authStore.cerrarSesion()
      toast.success('Sesión cerrada exitosamente')
      router.push('/')
    }

    return {
      authStore,
      handleLogout
    }
  }
}
</script>

<style lang="scss" scoped>
.home-page {
  min-height: 100vh;
  background: var(--color-background);
}

.navbar {
  background: var(--color-surface);
  border-bottom: 1px solid var(--color-border-light);
  position: sticky;
  top: 0;
  z-index: 100;
  box-shadow: var(--shadow-sm);
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 var(--spacing-lg);
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 70px;
}

.nav-brand {
  display: flex;
  align-items: center;
  gap: var(--spacing-sm);
  font-weight: 600;
  font-size: var(--font-size-lg);
  color: var(--color-text);
}

.brand-icon {
  font-size: var(--font-size-xl);
}

.nav-actions {
  display: flex;
  align-items: center;
  gap: var(--spacing-sm);
}

.main-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 var(--spacing-lg);
}

.hero-section {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--spacing-2xl);
  align-items: center;
  min-height: 80vh;
  padding: var(--spacing-2xl) 0;
}

.hero-content {
  .hero-title {
    font-size: var(--font-size-4xl);
    font-weight: 700;
    line-height: 1.1;
    color: var(--color-text);
    margin-bottom: var(--spacing-lg);
  }

  .hero-subtitle {
    font-size: var(--font-size-xl);
    color: var(--color-text-secondary);
    line-height: 1.6;
    margin-bottom: var(--spacing-xl);
  }
}

.hero-actions {
  display: flex;
  gap: var(--spacing-md);
}

.hero-visual {
  display: flex;
  justify-content: center;
  align-items: center;
}

.hero-card {
  background: var(--color-surface);
  border-radius: var(--radius-xl);
  box-shadow: var(--shadow-xl);
  border: 1px solid var(--color-border-light);
  padding: var(--spacing-xl);
  width: 100%;
  max-width: 300px;
  transform: rotate(5deg);
  transition: var(--transition);

  &:hover {
    transform: rotate(0deg) scale(1.05);
    box-shadow: var(--shadow-xl);
  }
}

.card-header {
  display: flex;
  align-items: center;
  gap: var(--spacing-md);
  margin-bottom: var(--spacing-lg);
}

.creator-avatar {
  width: 50px;
  height: 50px;
  background: var(--color-primary);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: var(--font-size-xl);
}

.creator-info {
  h4 {
    font-weight: 600;
    color: var(--color-text);
    margin-bottom: 2px;
  }

  p {
    color: var(--color-text-secondary);
    font-size: var(--font-size-sm);
  }
}

.card-content {
  p {
    color: var(--color-text-secondary);
    margin-bottom: var(--spacing-md);
  }
}

.donation-amount {
  text-align: center;
  padding: var(--spacing-md);
  background: var(--color-surface-dark);
  border-radius: var(--radius-md);

  .amount {
    display: block;
    font-size: var(--font-size-xl);
    font-weight: 600;
    color: var(--color-primary);
  }

  .label {
    font-size: var(--font-size-sm);
    color: var(--color-text-secondary);
  }
}

.features-section {
  padding-bottom: var(--spacing-2xl);
}

.section-title {
  text-align: center;
  font-size: var(--font-size-3xl);
  font-weight: 600;
  color: var(--color-text);
  margin-bottom: var(--spacing-2xl);
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: var(--spacing-xl);
}

.feature-card {
  text-align: center;
  padding: var(--spacing-xl);

  .feature-icon {
    font-size: 3rem;
    margin-bottom: var(--spacing-lg);
  }

  h3 {
    font-size: var(--font-size-xl);
    font-weight: 600;
    color: var(--color-text);
    margin-bottom: var(--spacing-md);
  }

  p {
    color: var(--color-text-secondary);
    line-height: 1.6;
  }
}

.footer {
  background: var(--color-surface);
  border-top: 1px solid var(--color-border-light);
  text-align: center;
  padding: var(--spacing-xl);
  color: var(--color-text-secondary);
}

/* Pantallas de escritorio grandes (1200px+) */
@media (min-width: 1200px) {
  .hero-card {
    max-width: 450px;
    padding: var(--spacing-2xl);
  }

  .creator-avatar {
    width: 60px;
    height: 60px;
    font-size: var(--font-size-2xl);
  }

  .creator-info h4 {
    font-size: var(--font-size-lg);
  }

  .donation-amount {
    padding: var(--spacing-lg);
    
    .amount {
      font-size: var(--font-size-2xl);
    }
  }
}

/* Pantallas de escritorio medianas (992px - 1199px) */
@media (min-width: 992px) and (max-width: 1199px) {
  .hero-card {
    max-width: 400px;
    padding: var(--spacing-xl);
  }

  .creator-avatar {
    width: 55px;
    height: 55px;
  }

  .donation-amount .amount {
    font-size: var(--font-size-xl);
  }
}

/* Tablets y pantallas medianas (769px - 991px) */
@media (min-width: 769px) and (max-width: 991px) {
  .hero-card {
    max-width: 350px;
  }
}

@media (max-width: 768px) {
  .nav-container {
    padding: 0 var(--spacing-md);
    height: auto;
    min-height: 70px;
    flex-wrap: wrap;
    align-items: center;
  }

  .nav-brand {
    font-size: var(--font-size-base);
    flex: 1;
  }

  .brand-icon  {
    font-size: var(--font-size-3xl);
  }

  .nav-actions {
    display: flex;
    flex-direction: row;
    gap: var(--spacing-xs);
    flex-shrink: 0;
    align-items: center;
  }

  .nav-actions .btn {
    padding: var(--spacing-xs) var(--spacing-sm);
    font-size: var(--font-size-sm);
    white-space: nowrap;
    min-width: auto;
  }

  .hero-section {
    grid-template-columns: 1fr;
    text-align: center;
    gap: var(--spacing-xl);
  }

  .hero-title {
    font-size: var(--font-size-3xl) !important;
  }

  .hero-subtitle {
    font-size: var(--font-size-lg) !important;
  }

  .hero-actions {
    justify-content: center;
    flex-direction: column;
  }

  .hero-card {
    transform: none;
  }

  .features-grid {
    grid-template-columns: 1fr;
    gap: var(--spacing-lg);
  }
}

/* Para pantallas muy pequeñas (móviles en modo portrait) */
@media (max-width: 480px) {
  .nav-container {
    flex-direction: column;
    gap: var(--spacing-sm);
    padding: var(--spacing-sm);
    align-items: stretch;
  }

  .nav-brand {
    justify-content: center;
    margin-bottom: var(--spacing-xs);
  }

  .brand-icon  {
    font-size: var(--font-size-3xl);
  }

  .nav-actions {
    justify-content: center;
    width: 100%;
  }

  .nav-actions .btn {
    flex: 1;
    text-align: center;
  }
}
</style>
