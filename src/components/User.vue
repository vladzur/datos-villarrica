<template>
  <div class="card">
    <div class="card-content">
      <div class="media">
        <div class="media-left">
          <figure class="image is-48x48">
            <img :src="user.photoUrl">
          </figure>
        </div>
        <div class="media-content">
          <p class="title is-4">{{user.name}}</p>
          <p class="subtitle is-6">{{user.email}}</p>
        </div>
      </div>
      <div class="content">
        <div class="control has-icon-left">
          <a class="button" @click="signOut">
            <span class="icon is-left">
              <i class="icon fa fa-sign-out"></i>
            </span>
            <span>Cerrar Sesión</span>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['user'],
  methods: {
    signOut () {
      this.$store.dispatch('logout')
    }
  }
}
</script>
