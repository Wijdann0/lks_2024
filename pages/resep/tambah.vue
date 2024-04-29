<template>
    <div class="container">
        <div class="row container justify-content-center pt-5 pb-5">
            <div class="col-lg-8">
                <h2>Kelola Resep</h2>
            </div>
        </div>
        <form @submit.prevent="tambahResep">
            <div class="row justify-content-around pb-4">
                <div class="col-lg-4">
                    <input v-model="resep.Tgl_Resep" class="form-control" type="date" placeholder="Tanggal Resep" aria-label="default input example">
                </div>

                <div class="col-lg-4">
                    <input v-model="resep.No_Resep" class="form-control" type="text" placeholder="No Resep" aria-label="default input example">
                </div>
            </div>
            <div class="row justify-content-around pb-4">
                <div class="col-lg-4">
                    <input v-model="resep.Nama_Dokter" class="form-control" type="text" placeholder="Nama Dokter" aria-label="default input example">
                </div>

                <div class="col-lg-4">
                    <input v-model="resep.Nama_Pasien" class="form-control" type="text" placeholder="Nama pasien" aria-label="default input example">
                </div>
            </div>
            <div class="row justify-content-around pb-5">
                <div class="col-lg-4">
                    <input v-model="resep.Obat_Resep" class="form-control" type="text" placeholder="Obat Resep" aria-label="default input example">
                </div>

                <div class="col-lg-4">
                    <input v-model="resep.Jumlah_Obat" class="form-control" type="number" placeholder="Jumlah" aria-label="default input example">
                </div>
            </div>
            <div class="row justify-content-center pb-4">
                <div class="col-lg-1">
                        <button class="btn btn-primary" type="submit">Tambah</button>
                </div>
            </div>
        </form>
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

const supa = useSupabaseClient();
  
  const resep = ref({
    Tgl_Resep: "",
    No_Resep: "",
    Nama_Dokter: "",
    Nama_Pasien: "",
    Obat_Resep: "",
    Jumlah_Obat: "",
  });
  
  const tambahResep = async () => {
    const { data, error } = await supa
    .from('Tbl_Resep')
    .insert([resep.value]);
    if (!error) {
        navigateTo ('/resep')
    } else {
        console.error('Failed to add resep:', error.message);
    }
  };
</script>

<style>

</style>