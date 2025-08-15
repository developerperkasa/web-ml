<template>
  <div class="app">
    <!-- Header -->
    <header class="header">
      <h1>TutorPuh_Sepuh</h1>
      <p class="subtitle">
        adalah sebuah website yang membantu anda untuk merancang build item Mobile Legends kamu agar
        makin gege dalam gameplay dan nggak jadi dark system.
      </p>
    </header>

    <!-- Search & Filter -->
    <div class="controls">
      <input type="text" v-model="searchQuery" placeholder="Cari item..." class="search" />
      <select v-model="selectedCategory" class="filter">
        <option value="">Semua Kategori</option>
        <option v-for="cat in categories" :key="cat">{{ cat }}</option>
      </select>
    </div>

    <!-- Grid Items -->
    <div class="grid">
      <div
        v-for="(it, index) in filteredItems"
        :key="it.id"
        class="card"
        :style="{ animationDelay: `${index * 0.08}s` }"
        @mousemove="handleMouseMove($event, index)"
        @mouseleave="resetGlow(index)"
      >
        <div class="image-wrapper">
          <img v-if="it.icon" :src="it.icon" :alt="it.name" />
          <div v-else class="no-image">No Image</div>
        </div>
        <h3 class="name">{{ it.name }}</h3>
        <p class="desc">{{ shortDesc(it.description) }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import items from '../../public/items.json'

export default {
  name: 'CariItem',
  data() {
    return {
      searchQuery: '',
      selectedCategory: '',
      items: items,
      categories: [],
    }
  },
  created() {
    // Ambil semua type unik dari items.json, filter undefined/null
    const types = items.map((item) => item.type).filter(Boolean)
    this.categories = [...new Set(types)]
  },
  computed: {
    filteredItems() {
      return this.items.filter((item) => {
        const matchSearch = item.name
          ? item.name.toLowerCase().includes(this.searchQuery.toLowerCase())
          : false
        const matchCategory = this.selectedCategory ? item.type === this.selectedCategory : true
        return matchSearch && matchCategory
      })
    },
  },
  methods: {
    shortDesc(desc) {
      if (!desc) return ''
      const words = desc.split(' ').slice(0, 5)
      return words.join(' ')
    },
    handleMouseMove(e, index) {
      const card = e.currentTarget
      const rect = card.getBoundingClientRect()
      const x = e.clientX - rect.left
      const y = e.clientY - rect.top
      card.style.setProperty('--mouse-x', `${x}px`)
      card.style.setProperty('--mouse-y', `${y}px`)
    },
    resetGlow(index) {
      // efek glow direset saat mouse keluar
    },
  },
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap');

.app {
  font-family: 'Poppins', sans-serif;
  padding: 20px;
  min-height: 100vh;
  background: linear-gradient(135deg, #202d40, #2f7498);
  position: relative;
  overflow: hidden;
  color: white;
}

/* Background subtle animasi */
.app::before {
  content: '';
  position: absolute;
  inset: 0;
  background-image: radial-gradient(rgba(255, 255, 255, 0.05) 1px, transparent 1px);
  background-size: 40px 40px;
  animation: movePattern 25s linear infinite;
  z-index: 0;
}
@keyframes movePattern {
  from {
    background-position: 0 0;
  }
  to {
    background-position: 40px 40px;
  }
}

.header {
  position: relative;
  z-index: 1;
  text-align: center;
  margin-bottom: 24px;
}
.header h1 {
  font-weight: 600;
  font-size: 2rem;
}
.subtitle {
  font-size: 1rem;
  opacity: 0.85;
  max-width: 600px;
  margin: 0 auto;
}

/* Controls */
.controls {
  position: relative;
  z-index: 1;
  display: flex;
  gap: 12px;
  margin-bottom: 24px;
  justify-content: center;
}
.search,
.filter {
  padding: 10px 14px;
  border-radius: 12px;
  border: none;
  outline: none;
  font-size: 14px;
  background: rgba(255, 255, 255, 0.15);
  color: white;
  backdrop-filter: blur(8px);
}
.search::placeholder {
  color: rgba(255, 255, 255, 0.7);
}
.filter option {
  background: #202d40;
  color: white;
}

/* Grid */
.grid {
  position: relative;
  z-index: 1;
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
  gap: 24px;
}

/* Card */
.card {
  position: relative;
  background: rgba(255, 255, 255, 0.07);
  border-radius: 16px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
  padding: 16px;
  text-align: center;
  transition:
    transform 0.3s ease,
    box-shadow 0.3s ease;
  animation: fadeInUp 0.6s ease forwards;
  opacity: 0;
  overflow: hidden;
  background: linear-gradient(135deg, #202d40, #2f7498);
  color: white;
  padding: 20px;
  width: 200px;
  border-top-left-radius: 0;
  border-top-right-radius: 20px;
  border-bottom-right-radius: 20px;
  border-bottom-left-radius: 80px;
  cursor: pointer;
}
.card::before {
  content: '';
  position: absolute;
  top: var(--mouse-y, 50%);
  left: var(--mouse-x, 50%);
  transform: translate(-50%, -50%);
  width: 200%;
  height: 200%;
  background: radial-gradient(linear, rgba(255, 255, 255, 0.15) 0%, transparent 60%);
  opacity: 0;
  transition: opacity 0.3s;
}
.card:hover::before {
  opacity: 1;
}
.card:hover {
  transform: translateY(-6px) scale(1.03);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.5);
}

/* Gambar Bulat */
.image-wrapper {
  width: 110px;
  height: 110px;
  margin: 0 auto 10px;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 50%;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
}
.image-wrapper img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.no-image {
  color: rgba(255, 255, 255, 0.7);
  font-size: 14px;
  font-weight: bold;
}

.name {
  margin: 8px 0 4px 0;
  font-size: 16px;
  font-weight: 600;
}
.desc {
  font-size: 13px;
  opacity: 0.8;
}

/* Animasi */
@keyframes fadeInUp {
  0% {
    opacity: 0;
    transform: translateY(15px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
