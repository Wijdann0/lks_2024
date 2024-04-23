<template>
    <div class="container">
    <div class="row container justify-content-center pt-5 pb-5">
        <div class="col-lg-8">
            <h2>Kelola Obat</h2>
        </div>
    </div>
    <form @submit.prevent="tambahObat"></form>
    <div class="row justify-content-around pb-4">
        <div class="col-lg-4">
            <input v-model="Code_Obat" class="form-control" type="text" placeholder="Kode Obat" aria-label="default input example">
        </div>

        <div class="col-lg-4">
            <input v-model="Jumlah" class="form-control" type="number" placeholder="Jumlah Obat" aria-label="default input example">
        </div>
    </div>
    <div class="row justify-content-around pb-4">
        <div class="col-lg-4">
            <input v-model="Nama_Obat" class="form-control" type="text" placeholder="Nama Obat" aria-label="default input example">
        </div>

        <div class="col-lg-4">
            <label for="">Exp Date</label>
            <input v-model="Expired_Date" class="form-control" type="date" placeholder="Expired Date" aria-label="default input example">
        </div>
    </div>
    <div class="row justify-content-around pb-5">
        <div class="col-lg-4">
            <input v-model="Harga" class="form-control" type="number" placeholder="Harga per Unit" aria-label="default input example">
        </div>
    </div>
    <div class="row justify-content-center pb-4">
        <div class="col-lg-1">
            <nuxt-link to="/obat">
                <button class="btn btn-primary" type="submit">Tambah</button>
            </nuxt-link>
        </div>
    </div>
    <div class="row justify-content-end">
        <div class="col-lg-2">
            <nuxt-link to="/obat">
                <button class="btn btn-light" type="submit">Data Obat</button>
            </nuxt-link>
        </div>
    </div>
</div>
</template>

<script setup>
const supa = useSupabaseClient()
const obat = ref({
    Kode_Obat: "",
    Jumlah: "",
    Nama_Obat: "",
    Expired_Date: "",
    Harga: "",
})

const tambahObat = async () => {
    const{error} = await supa.from('Tbl_Obat')
    .insert([obat.value]);

    if(!error) navigateTo('/obat')
}

</script>

<style>

</style>