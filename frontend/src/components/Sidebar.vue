<template>
  <div id="sidebar" class="sidebar" :class="{ isOpen: isOpen }">
    <div class="sidebar-opener" @click="toggle">Open</div>
    <ul class="sidebar-menu">
      <li class="sidebar-menu-item">
        <img class="zap-emoji" src="../assets/zap-emoji.svg" alt="Zap Emoji" />
      </li>
      <li class="sidebar-menu-item" v-for="item in menu" :key="item">{{ item }}</li>
      <li class="sidebar-menu-item--small" v-for="item in smallMenu" :key="item">{{ item }}</li>
    </ul>
  </div>
</template>

<style scoped>
/*
Sidebar styles...
 */
.sidebar {
  position: relative;
  width: 340px;
  height: 100vh;
  padding: 30px;
  background-color: #34495e;
  transform: translateX(100%);
  transition: transform 0.6s ease(out-cubic);
}

.sidebar.isOpen {
  transform: translateX(0);
}

.sidebar-opener {
  position: absolute;
  top: 20px;
  right: 100%;
  margin-right: 20px;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  cursor: pointer;
}

.sidebar-opener:hover {
  text-decoration: underline;
}

.sidebar-menu {
  font-weight: 600;
  color: #fff;
}

.sidebar-menu-item,
.sidebar-menu-item--small {
  cursor: pointer;
}

.sidebar-menu-item:hover,
.sidebar-menu-item--small:hover {
  text-decoration: underline;
}

.sidebar-menu-item+.sidebar-menu-item,
.sidebar-menu-item--small+.sidebar-menu-item,
.sidebar-menu-item+.sidebar-menu-item--small,
.sidebar-menu-item--small+.sidebar-menu-item--small {
  margin-top: 20px;
}

.sidebar-menu-item {
  font-size: 36px;
}

.sidebar-menu-item+.sidebar-menu-item--small {
  margin-top: 30px;
}

.sidebar-menu-item--small {
  font-size: 18px;
  font-weight: normal;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: #ecf0f1;
}

/* The famed Zap agency logo (TM) */
.zap-emoji {
  height: 120px;
}
</style>

<script>
export default {
  name: 'Sidebar',
  data: () => ({
    isOpen: false,
    menu: ['Home', 'Work', 'Contact'],
    smallMenu: ['Tips', 'Resources', 'Shenanigans']
  }),
  methods: {
    open() {
      this.openerText = 'Close'
      this.isOpen = true
    },
    close() {
      this.openerText = 'Open'
      this.isOpen = false
    },
    toggle() {
      if (this.isOpen) {
        this.close()
      } else {
        this.open()
      }
    }
  }
}
</script>
