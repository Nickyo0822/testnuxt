<template>
  <div>
    <NuxtRouteAnnouncer />
    <NavBar @update-tab="updateTab" />
    <transition name="fade">
      <Collection v-if="isCollectionVisible" />
    </transition>
    <Inventaire v-if="isInventaireVisible" />
    <span v-touch:swipe="swipeHandler">Swipe Here</span>
  </div>
</template>

<script>
  export default {
    data() {
      return { 
        tab: 'map',
        isCollectionVisible: false,
        isInventaireVisible: false
      }
    },
    methods: {
      updateTab(arg) {
        this.tab = arg
          if (this.tab == 'collection') {
            this.isCollectionVisible = !this.isCollectionVisible
          }

          if (this.tab == 'inventaire') {
            this.isInventaireVisible = !this.isInventaireVisible
          }
      }
    }
  }
</script>

<style>
  body {
    margin: 0;
    background: linear-gradient(rgba(0, 0, 255, 0.5), rgba(255, 255, 0, 0.5)),
                  url('assets/images/map.jpg');
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    height: 100vh;
  }

  .fade-enter-active, .fade-leave-active {
    transition: opacity 0.5s;
  }
  .fade-enter-from, .fade-leave-to {
    opacity: 0;
  }
  .fade-enter-to, .fade-leave {
    opacity: 1;
  }
</style>