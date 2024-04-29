<template>
  <div>
    <Navbar>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse justify-content-end p-5" id="navbarNavAltMarkup">
        <div class="navbar-nav p-5">
          <nuxt-link v-if="['Admin'].includes(user?.user_metadata.tipe)" to="/user" class="nav-link">User</nuxt-link>
          <nuxt-link v-if="['Admin','Apoteker'].includes(user?.user_metadata.tipe)" to="/obat" class="nav-link">Obat</nuxt-link>
          <nuxt-link v-if="['Admin','Apoteker'].includes(user?.user_metadata.tipe)" to="/resep" class="nav-link">Resep</nuxt-link>
          <nuxt-link v-if="['Admin','Kasir'].includes(user?.user_metadata.tipe)" to="/transaksi/transaksi" class="nav-link">Transaksi</nuxt-link>
          <nuxt-link v-if="['Admin'].includes(user?.user_metadata.tipe)" to="/laporan/lap" class="nav-link">Laporan</nuxt-link>
          <nuxt-link v-if="['Admin'].includes(user?.user_metadata.tipe)" to="/log" class="nav-link">Log Act.</nuxt-link>
          <nuxt-link to="/logout" class="nav-link text-danger">Log out</nuxt-link>
        </div>
      </div>
    </Navbar>
    <slot />
  </div>
</template>

<script setup>
const user = useSupabaseUser()
</script>

<style>
#navbarNavAltMarkup {
  font-size: 20px;
}
</style>