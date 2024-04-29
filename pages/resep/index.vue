<template>
    <div class="container">
          <div class="row pt-5">
              <div class="col-lg-8 d-flex justify-content-center">
              <h2>Data Resep</h2>
          </div>
          <div class="col-lg-1 d-flex justify-content-center">
              <nuxt-link to="/resep/tambah">
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
                        <th scope="col">#</th>
                        <th scope="col">No Resep</th>
                        <th scope="col">Tgl Resep</th>
                        <th scope="col">Nama Dokter</th>
                        <th scope="col">Obat Yang Dibeli</th>
                      </tr>
                    </thead>
                    <tbody>
                      <tr v-for="(rsp , i) in resep" :key="i">
                        <th scope="row">{{ 1 + i }}</th>
                        <td>{{ rsp.No_Resep }}</td>
                        <td>{{ rsp.Tgl_Resep }}</td>
                        <td>{{ rsp.Nama_Dokter }}</td>
                        <td>{{ rsp.Obat_Resep}}</td>
                      </tr>
                    </tbody>
                  </table>
            </div>
          </div>
        </div>
  </template>
        
<script setup>
const supa = useSupabaseClient()

const resep = ref([])

const getResep = async () => {
  const {data,error} = await supa.from('Tbl_Resep').select()

  if(data){
    resep.value = data
  }
}

onMounted(() => {
  getResep()
})
</script>
  
<style scoped>
  .tbl {
      background-color: #83A0C3;
      box-shadow: 1px 1px 50px #83A0C3;
  }
</style>
  