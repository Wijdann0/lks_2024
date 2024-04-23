<template>
  <div class="container">
        <div class="row pt-5">
            <div class="col-lg-8 d-flex justify-content-center">
            <h2>Data Obat</h2>
        </div>
        <div class="col-lg-1 d-flex justify-content-center">
            <nuxt-link to="/obat/tambah">
            <button class="btn btn-primary" type="submit">Tambah</button>
            </nuxt-link>
        </div>
        <div class="col-lg-1 d-flex justify-content-center">
            <nuxt-link to="#">
            <button class="btn btn-primary" type="submit">Edit</button>
            </nuxt-link>
        </div>
        <div class="col-lg-1 d-flex justify-content-center">
            <nuxt-link to="#">
            <button class="btn btn-primary" type="submit">Hapus</button>
            </nuxt-link>
        </div>
        </div>
        <div class="row  justify-content-center">
          <div class="col-lg-10 mt-5 rounded-4 tbl">
              <table class="table  border-dark">
                  <thead>
                    <tr>
                      <th scope="col">Id Obat</th>
                      <th scope="col">Kode Obat</th>
                      <th scope="col">Nama Obat</th>
                      <th scope="col">Exp Date</th>
                      <th scope="col">Jumlah</th>
                    </tr>
                  </thead>
                  <tbody>
                    <tr v-for="(obt ,i) in Obt" :key="i">
                      <th scope="row">{{ 1 + i }}</th>
                      <td>{{ obt.Code_Obat }}</td>
                      <td>{{ obt.Nama_Obat }}</td>
                      <td>{{ obt.Expired_Date }}</td>
                      <td>{{ obt.Jumlah }}</td>
                    </tr>
                  </tbody>
                </table>
          </div>
        </div>
      </div>
</template>
      
<script setup>
const supa = useSupabaseClient()

const Obt = ref([])

const getObat = async () => {
  const {data,error} = await supa
  .from('Tbl_Obat')
  .select('*')
  .order('id')

  if(!error){
    Obt.value = data
  }else{
    console.log('error')
  }
}

onMounted(() => {
  getObat()
}

)
</script>

<style scoped>
.tbl {
    background-color: #83A0C3;
    box-shadow: 1px 1px 50px #83A0C3;
}
</style>
