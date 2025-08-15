<template>
  <div class="beranda-app">
    <div class="intro-container">
      <div class="main-image">
        <img src="" alt="Ling Collector" />
      </div>
      <div class="slogan">
        <h1>TutorPuh_Sepuh</h1>
        <p>
          adalah sebuah website yang membantu anda untuk merancang build item Mobile Legends kamu
          agar makin gege dalam gameplay dan nggak jadi dark system.
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
// Tidak perlu script khusus untuk halaman perkenalan ini
</script>

<style scoped>
.beranda-app {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(135deg, #202d40, #2f7498);
  font-family: 'Poppins', sans-serif;
  color: white;
  padding: 40px 0;
}

.intro-container {
  display: flex;
  align-items: center;
  gap: 48px;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 32px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.25);
  padding: 48px 40px;
}

.main-image img {
  width: 260px;
  height: 260px;
  object-fit: cover;
  border-radius: 24px;
  box-shadow: 0 4px 24px rgba(0, 0, 0, 0.4);
  background: #1a2636;
}

.slogan {
  max-width: 400px;
}

.slogan h1 {
  font-size: 2.5rem;
  font-weight: 700;
  margin-bottom: 18px;
  letter-spacing: 1px;
}

.slogan p {
  font-size: 1.15rem;
  line-height: 1.7;
  opacity: 0.92;
}
</style>
