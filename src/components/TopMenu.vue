<template>
  <nav class="navbar">
    <div class="navbar-brand">
      <router-link class="navbar-item" to="/" exact>
        <i class="icon fa fa-home"></i>DatosVillarrica
      </router-link>
      <div class="navbar-burger burger" @click="toggleMenu" :class="{'is-active': navmenu}">
        <span></span>
        <span></span>
        <span></span>
      </div>
    </div>
    <div class="navbar-menu" :class="{'is-active': navmenu}">
      <div class="navbar-start">
        <router-link class="navbar-item" to="/announcements" exact>Anuncios</router-link>
      </div>
      <div class="navbar-end">
        <router-link v-if="user" class="navbar-item" to="/profile" exact>
          <i class="icon fa fa-user"></i>{{user.name}}
        </router-link>
        <router-link v-else class="navbar-item" to="/login" exact>
          <i class="icon fa fa-sign-in"></i>Iniciar Sesión
        </router-link>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data () {
    return {
      navmenu: false
    }
  },
  methods: {
    toggleMenu () {
      this.navmenu = !this.navmenu
    }
  },
  computed: {
    user () {
      return this.$store.getters.user
    }
  }
}
</script>
