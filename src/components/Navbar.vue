<template>
  <nav class="navbar">
    <div class="navbar-container">
      <div class="navbar-brand">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          preserveAspectRatio="xMidYMid meet"
          version="1.0"
          viewBox="-0.0 0.0 73.7 71.7"
          zoomAndPan="magnify"
          style="fill: rgb(224, 226, 225)"
          original_string_length="2319"
          width="82.787923285801px"
          height="80.53007083255189px"
        >
          <g data-name="32" id="__id0_smg04hq4ya">
            <path
              d="M66.44,0H34.71c-4.39,1.16-7.07,3.82-7.37,8.65.03.93.06,1.86.09,2.78,0,1.7-.01,3.28,0,4.87,0,2.45-.02,4.91-.01,7.36H7.24A9.494,9.494,0,0,0,0,30.55V51.23A6.744,6.744,0,0,0,1.07,54.2a7.5,7.5,0,0,0,3.38,2.61,9.858,9.858,0,0,0,4.2.97h2.31v6.58c.06,2.44.13,4.89.19,7.34,1.18-1.12,2.19-2.1,2.98-2.87,2.48-2.43,3.69-3.67,5.19-5.27,1.27-1.34,1.33-1.42,1.93-2.04,2.74-2.86,3.46-3.2,3.83-3.35a5.407,5.407,0,0,1,2.34-.43c3.38.13,6.77.06,10.16.04a8.314,8.314,0,0,0,8.66-8.69c.03-3.04.01-6.09.01-9.13V35.1l.03-1.02a5.348,5.348,0,0,1,2.32.43c.36.15,1.08.48,3.82,3.35.6.62.67.7,1.93,2.04,1.51,1.6,2.72,2.84,5.2,5.27.78.77,1.79,1.75,2.98,2.87q.09-3.675.18-7.34V34.12h2.32a9.85,9.85,0,0,0,4.19-.97,7.525,7.525,0,0,0,3.38-2.61,6.775,6.775,0,0,0,1.08-2.98V6.89A9.509,9.509,0,0,0,66.44,0ZM43.48,49.09a5.552,5.552,0,0,1-5.92,5.93c-3.91.03-7.81.05-11.72-.02a3.773,3.773,0,0,0-3.02,1.26c-1.44,1.48-3.04,2.81-4.36,4.4a38.593,38.593,0,0,1-4.92,4.93c.03-.78.14-4.46.19-8.48a2.218,2.218,0,0,0-.52-1.68,2.038,2.038,0,0,0-1.52-.41c-1.03.04-2.07.02-3.1,0a5.6,5.6,0,0,1-5.82-5.89q-.045-8.34,0-16.7a5.611,5.611,0,0,1,5.79-5.94q9.465-.045,18.93-.03a8.186,8.186,0,0,0,4.39,6.69,9.359,9.359,0,0,0,4.21.97c1.12.01,2.24.02,3.36.02,1.34.02,2.69.02,4.03,0Q43.525,41.61,43.48,49.09ZM70.91,25.47a5.607,5.607,0,0,1-5.83,5.89c-1.03.02-2.07.04-3.1,0a1.97,1.97,0,0,0-1.51.41,2.23,2.23,0,0,0-.53,1.68c.05,4.02.17,7.69.19,8.48A39.274,39.274,0,0,1,55.21,37c-1.31-1.59-2.92-2.92-4.35-4.4a3.78,3.78,0,0,0-3.03-1.26c-.53.01-1.06.02-1.59.02-.95.01-1.89.02-2.84.02-2.43.01-4.86-.01-7.29-.02-3.26-.03-5.44-1.87-5.84-4.9a6.826,6.826,0,0,1-.08-1.03V23.66c-.02-4.98-.03-9.96,0-14.94A5.548,5.548,0,0,1,36,2.83q14.55-.075,29.12,0a5.611,5.611,0,0,1,5.79,5.94Q70.955,17.125,70.91,25.47ZM64.929,13.491H36.591a1.5,1.5,0,0,1,0-3H64.929A1.5,1.5,0,0,1,64.929,13.491ZM54.808,21.443H37.459a1.5,1.5,0,0,1,0-3H54.808A1.5,1.5,0,0,1,54.808,21.443ZM37.083,46.152H8.745a1.5,1.5,0,0,1,0-3H37.083A1.5,1.5,0,0,1,37.083,46.152ZM8.866,35.1H26.215a1.5,1.5,0,0,1,0,3H8.866A1.5,1.5,0,0,1,8.866,35.1Z"
              style="fill: inherit"
            />
          </g>
        </svg>
        <h2 class="brand-text">TutorPuh_Sepuh</h2>
      </div>

      <div class="navbar-menu">
        <!-- <router-link to="/beranda" class="nav-link" active-class="active"> About </router-link>

        <router-link to="/build-item" class="nav-link" active-class="active">
          Build Item
        </router-link> -->
        <router-link to="/cari-item" class="nav-link" active-class="active">
          Cari Item
        </router-link>
      </div>

      <div class="navbar-toggle" @click="toggleMenu">
        <span class="hamburger"></span>
        <span class="hamburger"></span>
        <span class="hamburger"></span>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return {
      isMenuOpen: false,
    }
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen
      const menu = document.querySelector('.navbar-menu')
      if (this.isMenuOpen) {
        menu.classList.add('active')
      } else {
        menu.classList.remove('active')
      }
    },
  },
}
</script>

<style scoped>
body {
  font-family: Arial, Helvetica, sans-serif;
}
.navbar {
  background: linear-gradient(135deg, #202d40, #2f7498);
  margin: 0px;
  padding: 0px auto;

  position: sticky;
  top: 0;

  z-index: 1000;
}

.navbar-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px 20px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 60px;
  font-family: Arial, Helvetica, sans-serif;
}

.navbar-brand {
  display: flex;
  align-items: center;
}

.brand-text {
  color: #333333;
  font-size: 1.5rem;
  font-weight: 600;
  margin: 0;
}
.brand-text {
  color: #f8f8f8;
}
.navbar-menu {
  display: flex;
  align-items: center;
  gap: 30px;
  background: transparent;
  border-radius: 20px;
}
.navbar-menu:hover {
  display: flex;
  align-items: center;
  gap: 30px;
  background: transparent;
}
.navbar-menu.active {
  display: flex;
  align-items: center;
  gap: 30px;
  background: transparent;
}
.nav-link {
  color: #ffff;
  text-decoration: none;
  font-weight: 700;
  font-size: 0.95rem;
  padding: 12px 40px;
  border-radius: 50px;
  transition: all 0.2s ease;
  background: linear-gradient(135deg, #202d40, #2f7498);
}

.nav-link:hover {
  color: #ffff;
  background: linear-gradient(135deg, #202d40, #2f7498);
}

.nav-link.active {
  color: #ffff;
  background: linear-gradient(135deg, #202d40, #2f7498);
  font-weight: 800;
}

.navbar-toggle {
  display: none;
  flex-direction: column;
  cursor: pointer;
  padding: 8px;
}

.hamburger {
  width: 20px;
  height: 2px;
  background: #333333;
  margin: 2px 0;
  border-radius: 1px;
  transition: 0.2s ease;
}

/* Responsive Design */
@media (max-width: 768px) {
  .navbar-menu {
    position: fixed;
    top: 60px;
    left: -100%;
    width: 100%;
    height: calc(100vh - 60px);
    background: linear-gradient(135deg, #202d40, #2f7498);
    flex-direction: column;
    justify-content: flex-start;
    padding-top: 20px;
    gap: 0;
    transition: left 0.3s ease;
    border-top: 1px solid #e5e5e5;
  }

  .navbar-menu.active {
    left: 0;
  }

  .navbar-toggle {
    display: flex;
  }

  .nav-link {
    font-size: 1rem;
    padding: 15px 20px;
    width: 100%;
    border-bottom: 1px solid #f0f0f0;
    border-radius: 0;
  }

  .nav-link:hover {
    background: #f8f8f8;
  }

  .nav-link.active {
    background: #f0f0f0;
    border-left: 3px solid #333333;
  }
}

@media (max-width: 480px) {
  .navbar-container {
    padding: 0 15px;
  }

  .brand-text {
    font-size: 1.3rem;
  }
}
</style>
