<template>
    <div class="container">
        <div class="row container justify-content-center pt-5 pb-5">
            <div class="col-lg-8">
                <h2>Kelola Resep</h2>
            </div>
        </div>

        <div class="row justify-content-around pb-4">
            <div class="col-lg-4">
                <input class="form-control" type="text" placeholder="Tanggal Resep" aria-label="default input example">
            </div>

            <div class="col-lg-4">
                <input class="form-control" type="text" placeholder="No Resep" aria-label="default input example">
            </div>
        </div>
        <div class="row justify-content-around pb-4">
            <div class="col-lg-4">
                <input class="form-control" type="text" placeholder="Nama Dokter" aria-label="default input example">
            </div>

            <div class="col-lg-4">
                <input class="form-control" type="text" placeholder="Nama pasien" aria-label="default input example">
            </div>
        </div>
        <div class="row justify-content-around pb-5">
            <div class="col-lg-4">
                <input class="form-control" type="text" placeholder="Obat Resep" aria-label="default input example">
            </div>

            <div class="col-lg-4">
                <input class="form-control" type="text" placeholder="Jumlah" aria-label="default input example">
            </div>
        </div>
        <div class="row justify-content-center pb-4">
            <div class="col-lg-1">
                <nuxt-link to="/">
                    <button class="btn btn-primary" type="submit">Tambah</button>
                </nuxt-link>
            </div>
        </div>
        <div class="row justify-content-end">
            <div class="col-lg-2">
                <nuxt-link to="/resep">
                    <button class="btn btn-light" type="submit">Data Resep</button>
                </nuxt-link>
            </div>
        </div>
    </div>
</template>

<script setup>

</script>

<style>

</style>