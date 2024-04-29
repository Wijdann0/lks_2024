<template>
    <div class="container">
    <div class="row container justify-content-center pt-5 pb-5">
        <div class="col-lg-8">
            <h2>Transaksi</h2>
        </div>
    </div>

    <div class="row justify-content-around pb-4">
        <div class="col-lg-4">
            <input class="form-control" type="text" placeholder="Tipe Resep" aria-label="default input example">
        </div>

        <div class="col-lg-4">
            <input class="form-control" type="text" placeholder="Nama Dokter" aria-label="default input example">
        </div>
    </div>
    <div class="row justify-content-around pb-4">
        <div class="col-lg-4">
            <input class="form-control" type="text" placeholder="No Resep" aria-label="default input example">
        </div>

        <div class="col-lg-4">
            <select v-model="harga">
                <option disabled value="">Nama Obat</option>
                <option v-for="(obat ,i) in obats" :value="obat.Harga">{{ obat.Nama_Obat }}</option>
            </select>
        </div>
    </div>
    <div class="row justify-content-around pb-4">
        <div class="col-lg-4">
            <input class="form-control" type="text" placeholder="Tgl Resep" aria-label="default input example">
        </div>

        <div class="col-lg-4">
            <input class="form-control" type="text" placeholder="Nama Pasien" aria-label="default input example">
        </div>
    </div>
    <div class="row justify-content-around pb-4">
        <div class="col-lg-4">
            <input v-model="harga" class="form-control" type="text" placeholder="Harga" aria-label="default input example" readonly>
        </div>

        <div class="col-lg-4">
            <input v-model="jumlah" class="form-control" type="text" placeholder="Jumlah" aria-label="default input example">
        </div>
    </div>
    <div class="row justify-content-around pb-5">
        <div class="col-lg-4">
            <input v-model="total" class="form-control" type="text" placeholder="Total" aria-label="default input example" readonly>
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
            <nuxt-link to="/transaksi">
                <button class="btn btn-light" type="submit">Riwayat</button>
            </nuxt-link>
        </div>
    </div>
</div>
</template>

<script setup>
const supa = useSupabaseClient()
const user = useSupabaseUser()

const jumlah = ref(0)
const harga = ref(0)
const total = computed(() => jumlah.value * harga.value)

const obats = ref([])

const getObat = async () => {
  const {data,error} = await supa
  .from('Tbl_Obat')
  .select('*')
  .order('id')

  if(!error){
    obats.value = data
  }else{
    console.log('error')
  }
}

onMounted(() => {
  getObat()
})
</script>

<style>

</style>