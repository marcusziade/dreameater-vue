<template>
  <div class="container mx-auto px-4 py-8">
    <header class="text-center mb-12">
      <h1 class="text-4xl font-bold mb-2">{{ appName }}</h1>
      <p class="text-xl text-gray-600">{{ appDescription }}</p>
    </header>

    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mb-12">
      <div v-for="(screenshot, index) in screenshots" :key="index" class="rounded-lg overflow-hidden shadow-lg">
        <img :src="screenshot" :alt="`App Screenshot ${index + 1}`" class="w-full h-auto" />
      </div>
    </div>

    <div class="text-center">
      <a :href="appStoreLink" target="_blank" rel="noopener noreferrer"
        class="inline-block bg-blue-500 text-white font-bold py-3 px-6 rounded-full text-lg hover:bg-blue-600 transition duration-300">
        Download on the App Store
      </a>
    </div>

    <footer class="mt-12 text-center text-gray-600">
      <p>&copy; {{ new Date().getFullYear() }} {{ appName }}. All rights reserved.</p>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'AppLandingPage',
  data() {
    return {
      appName: 'Dreameater',
      appDescription: 'Dreameater is an iOS app that allows you to journal your dreams.',
      screenshots: [
        require('@/assets/dreameater1.png'),
        require('@/assets/dreameater2.png'),
        require('@/assets/dreameater3.png'),
        require('@/assets/dreameater4.png'),
        require('@/assets/dreameater5.png'),
      ],
      appStoreLink: 'https://apps.apple.com/us/app/dreameater/id6474666426',
    }
  }
}
</script>