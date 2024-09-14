<template>
  <div class="app-container">
    <div class="content-wrapper">
      <header class="header">
        <h1>{{ appName }}</h1>
        <p>{{ appDescription }}</p>
      </header>
      
      <div class="screenshots-container">
        <div class="screenshots-scroll">
          <img v-for="(screenshot, index) in screenshots" 
               :key="index" 
               :src="screenshot" 
               :alt="`App Screenshot ${index + 1}`" 
               class="screenshot-image" />
        </div>
      </div>
      
      <div class="cta-button">
        <a :href="appStoreLink" target="_blank" rel="noopener noreferrer">
          Download on the App Store
        </a>
      </div>
      <div class="features-grid">
        <div v-for="feature in features" :key="feature.title" class="feature-card">
          <h3>{{ feature.title }}</h3>
          <p>{{ feature.description }}</p>
        </div>
      </div>
      <footer class="footer">
        <p>&copy; {{ currentYear }} {{ appName }}. All rights reserved.</p>
      </footer>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AppLandingPage',
  data() {
    return {
      appName: 'Dream Eater',
      appDescription: 'Journal your dreams and unlock the power of your subconscious',
      screenshots: [
        require('@/assets/dreameater1.png'),
        require('@/assets/dreameater2.png'),
        require('@/assets/dreameater6.png'),
        require('@/assets/dreameater3.png'),
        require('@/assets/dreameater4.png'),
        require('@/assets/dreameater5.png'),
      ],
      appStoreLink: 'https://apps.apple.com/us/app/dreameater/id6474666426',
      features: [
        { title: 'Dream Journal', description: 'Easily record and organize your dreams with our intuitive interface.' },
        { title: 'Dream Analysis', description: 'Gain insights into your subconscious mind with our ML-powered dream analysis.' },
        { title: 'Dream Insights', description: 'Discover recurring themes and symbols in your dreams over time.' },
      ],
    }
  },
  computed: {
    currentYear() {
      return new Date().getFullYear();
    }
  }
}
</script>

<style scoped>
.app-container {
  background: linear-gradient(to bottom, #e6f2ff, #ffffff);
  min-height: 100vh;
}

.content-wrapper {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
}

.header {
  text-align: center;
  margin-bottom: 3rem;
}

.header h1 {
  font-size: 2.5rem;
  color: #1a365d;
  margin-bottom: 0.5rem;
}

.header p {
  font-size: 1.25rem;
  color: #4a5568;
}

.screenshots-container {
  margin-bottom: 3rem;
  overflow-x: auto;
}

.screenshots-scroll {
  display: flex;
  gap: 1rem;
}

.screenshot-image {
  height: 400px;
  width: auto;
  object-fit: cover;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.cta-button {
  text-align: center;
  margin-bottom: 3rem;
}

.cta-button a {
  display: inline-block;
  background-color: #3182ce;
  color: white;
  font-weight: bold;
  padding: 1rem 2rem;
  border-radius: 9999px;
  text-decoration: none;
  font-size: 1.25rem;
  transition: background-color 0.3s;
}

.cta-button a:hover {
  background-color: #2c5282;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
  margin-bottom: 3rem;
}

.feature-card {
  background-color: white;
  padding: 1.5rem;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.feature-card h3 {
  font-size: 1.25rem;
  color: #1a365d;
  margin-bottom: 0.5rem;
}

.feature-card p {
  color: #4a5568;
}

.footer {
  text-align: center;
  color: #4a5568;
}
</style>