<template>
  <div class="container">
    <div class="row pp d-flex justify-content-center">
      <div class="col-lg-12 ">
        <h1>Hallo Selamat Datang</h1>
        <h3>{{ user.user_metadata.tipe_user }}</h3>
      </div>
    </div>
  </div>
</template>

<script setup>
const user = useSupabaseUser()

</script>

<style>
</style>