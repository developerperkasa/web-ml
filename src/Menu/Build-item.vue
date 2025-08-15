<template>
  <div class="build-app">
    <header class="build-header">
      <h1>Builder Item Mobile Legends</h1>
      <p>
        Pilih hero utama dan lawan, lalu buat build item terbaik untuk menghadapi musuh!
      </p>
    </header>
    <div class="build-controls">
      <div class="select-group">
        <label>Hero Utama:</label>
        <select v-model="selectedHero">
          <option value="">Pilih Hero</option>
          <option v-for="hero in heroes" :key="hero">{{ hero }}</option>
        </select>
      </div>
      <div class="select-group">
        <label>Hero Lawan:</label>
        <select v-model="selectedEnemy">
          <option value="">Pilih Hero Lawan</option>
          <option v-for="hero in heroes" :key="hero + '-enemy'">{{ hero }}</option>
        </select>
      </div>
      <button @click="generateBuild" :disabled="!selectedHero || !selectedEnemy">
        Generate Build
      </button>
    </div>
    <div class="build-result" v-if="buildItems.length">
      <h2>Rekomendasi Build untuk {{ selectedHero }} vs {{ selectedEnemy }}</h2>
      <div class="item-list">
        <div class="item-card" v-for="(item, idx) in buildItems" :key="idx">
          <div class="item-image no-image">No Image</div>
          <div class="item-info">
            <div class="item-name">{{ item.name }}</div>
            <div class="item-type">{{ item.type }}</div>
            <div class="item-price">Harga: {{ item.price }}</div>
          </div>
        </div>
      </div>
    </div>
    <div v-else class="build-placeholder">
      <p>Silakan pilih hero utama dan lawan, lalu klik Generate Build.</p>
    </div>
  </div>
</template>

<script>
// Contoh data, biasanya diambil dari router.js atau store
const fdata = {
  heroes: [
    "Ling", "Aldous", "Lancelot", "Hayabusa", "Gusion"
  ],
  items: [
    { name: "Berserker's Fury", type: "Physical", price: 2390 },
    { name: "Blade of Despair", type: "Physical", price: 3010 },
    { name: "Endless Battle", type: "Physical", price: 2330 },
    { name: "Athena's Shield", type: "Defense", price: 2150 },
    { name: "Immortality", type: "Defense", price: 2120 },
    { name: "Genius Wand", type: "Magic", price: 2000 },
    { name: "Glowing Wand", type: "Magic", price: 2200 }
  ]
}

export default {
  name: "BuildItem",
  data() {
    return {
      heroes: fdata.heroes,
      items: fdata.items,
      selectedHero: "",
      selectedEnemy: "",
      buildItems: []
    }
  },
  methods: {
    generateBuild() {
      // Contoh logika sederhana: jika lawan magic, rekomendasi defense/magic resist
      if (this.selectedEnemy === "Gusion" || this.selectedEnemy === "Hayabusa") {
        this.buildItems = this.items.filter(item => item.type === "Defense")
      } else if (this.selectedEnemy === "Aldous") {
        this.buildItems = this.items.filter(item => item.type === "Physical")
      } else {
        // Default: campur 3 item physical, 1 defense, 1 magic
        this.buildItems = [
          ...this.items.filter(i => i.type === "Physical").slice(0, 3),
          ...this.items.filter(i => i.type === "Defense").slice(0, 1),
          ...this.items.filter(i => i.type === "Magic").slice(0, 1)
        ]
      }
    }
  }
}
</script>

<style scoped>
.build-app {
  min-height: 100vh;
  background: linear-gradient(135deg, #202d40, #2f7498);
  color: white;
  font-family: 'Poppins', sans-serif;
  padding: 32px 0;
}
.build-header {
  text-align: center;
  margin-bottom: 32px;
}
.build-header h1 {
  font-size: 2rem;
  font-weight: 700;
  margin-bottom: 10px;
}
.build-controls {
  display: flex;
  justify-content: center;
  gap: 24px;
  margin-bottom: 32px;
  flex-wrap: wrap;
}
.select-group {
  display: flex;
  flex-direction: column;
  gap: 6px;
}
select {
  padding: 8px 12px;
  border-radius: 8px;
  border: none;
  background: rgba(255,255,255,0.12);
  color: white;
  font-size: 1rem;
  outline: none;
}
button {
  padding: 10px 22px;
  border-radius: 10px;
  border: none;
  background: #2f7498;
  color: white;
  font-weight: 600;
  font-size: 1rem;
  cursor: pointer;
  transition: background 0.2s;
}
button:disabled {
  background: #888;
  cursor: not-allowed;
}
.build-result {
  max-width: 800px;
  margin: 0 auto;
  background: rgba(255,255,255,0.07);
  border-radius: 18px;
  padding: 32px 24px;
  box-shadow: 0 4px 24px rgba(0,0,0,0.18);
}
.item-list {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
  margin-top: 18px;
}
.item-card {
  background: rgba(255,255,255,0.09);
  border-radius: 14px;
  padding: 16px 12px;
  width: 160px;
  text-align: center;
  box-shadow: 0 2px 10px rgba(0,0,0,0.13);
  display: flex;
  flex-direction: column;
  align-items: center;
}
.item-image {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  background: #1a2636;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #bbb;
  font-size: 15px;
  margin-bottom: 10px;
  border: 2px solid #2f7498;
}
.no-image {
  font-weight: bold;
}
.item-info {
  color: white;
}
.item-name {
  font-size: 1.1rem;
  font-weight: 600;
  margin-bottom: 4px;
}
.item-type {
  font-size: 0.95rem;
  opacity: 0.8;
  margin-bottom: 2px;
}
.item-price {
  font-size: 0.92rem;
  opacity: 0.7;
}
.build-placeholder {
  text-align: center;
  margin-top: 40px;
  font-size: 1.1rem;
}
