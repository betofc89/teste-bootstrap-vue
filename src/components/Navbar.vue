<template>
  <b-navbar toggleable type="dark" variant="dark">
    <b-navbar-brand href="#">NavBar</b-navbar-brand>

    <b-navbar-toggle target="navbar-toggle-collapse">
      <template #default="{ expanded }">
        <b-icon v-if="expanded" icon="chevron-bar-up"></b-icon>
        <b-icon v-else icon="chevron-bar-down"></b-icon>
      </template>
    </b-navbar-toggle>

    <b-collapse id="navbar-toggle-collapse" is-nav>
      <b-navbar-nav class="ml-auto">
        <b-nav-item href="#"><router-link to="/">Home</router-link></b-nav-item>
        <b-nav-item href="#"
          ><router-link to="/modal">Modal</router-link></b-nav-item
        >
        <b-nav-item href="#"
          ><router-link to="/modal2">Modal</router-link></b-nav-item
        >
        <b-nav-item href="#"
          ><router-link to="/carousel">Carousel</router-link></b-nav-item
        >
        <b-nav-item href="#"
          ><router-link to="/sidebar">Sidebar</router-link></b-nav-item
        >
        <b-nav-item href="#"
          ><router-link to="/toasts">Toasts</router-link></b-nav-item
        >
        <b-nav-item href="#"
          ><router-link to="/tabs">Tabs</router-link></b-nav-item
        >
        <b-nav-item href="#"
          ><router-link to="/table">Table</router-link></b-nav-item
        >
        <b-nav-item href="#"
          ><router-link to="/progress">Progress</router-link></b-nav-item
        >
        <b-nav-item href="#"
          ><router-link to="/scrollspy">Scrollspy</router-link></b-nav-item
        >
        <b-nav-item href="#" disabled>Disabled</b-nav-item>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</template>

<script>
export default {};
</script>

<style></style>
