<template>
  <div id="sidebar" class="sidebar" :class="{ isOpen: isOpen }">
    <div class="sidebar-opener" @click="toggle">{{ openerText }}</div>
    <ul class="sidebar-menu">
      <li class="sidebar-menu-item">
        <img class="zap-emoji" src="../assets/zap-emoji.svg" alt="Zap Emoji" />
      </li>
      <li class="sidebar-menu-item" v-for="item in menu" :key="item">{{ item }}</li>
      <li class="sidebar-menu-item--small" v-for="item in smallMenu" :key="item">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Sidebar',
  data: () => ({
    openerText: 'Open',
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
