<template>
  <div class="container">
    <div class="row justify-content-center pt-5">
      <div class="col-lg-8">
        <h2>Log Activity</h2>
      </div>
    </div>
    <div class="row justify-content-center">
      <div class="col-lg-10 mt-5 rounded-4 tbl">
        <table class="table border-dark">
          <thead>
            <tr>
              <th scope="col">#</th>
              <th scope="col">User</th>
              <th scope="col">Waktu</th>
              <th scope="col">Aktivitas</th>
              <th scope="col">Tipe User</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(act, i) in Act" :key="i">
              <th>{{ i + 1 }}</th>
              <td>{{ act.username }}</td>
              <td>{{ act.waktu }}</td>
              <td>{{ act.aktivitas }}</td>
              <td>{{ act.tipe_user }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script setup>
const supa = useSupabaseClient()

const Act = ref([])

const getPengunjung = async () => {
  const { data, error } = await supa
    .from('Tbl_LogActivity')
    .select('*')
    .order('id')

  if (error) {
    console.error('Error fetching data:', error.message)
  } else {
    Act.value = data
  }
}

onMounted(() => {
  getPengunjung()
})
</script>

<style scoped>
.tbl {
  background-color: #83A0C3;
  box-shadow: 1px 1px 50px #83A0C3;
}
</style>



<!-- <template>
  <div class="container">
    <div class="row justify-content-center pt-5">
      <div class="col-lg-8">
        <h2>Log Activity</h2>
      </div>
    </div>
    <div class="row justify-content-center">
      <div class="col-lg-10 mt-5 rounded-4 tbl">
        <table class="table border-dark">
          <thead>
            <tr>
              <th scope="col">#</th>
              <th scope="col">user</th>
              <th scope="col">Waktu</th>
              <th scope="col">Aktivitas</th>
              <th scope="col">Tipe User</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(act,i ) in act" :key="i">
              <th>{{ i + 1 }}</th>
              <td>{{ act.username }}</td>
              <td>{{ act.Waktu }}</td>
              <td>{{ act.Aktivitas }}</td>
              <td>{{ act.tipe_user }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>

</template>

<script setup>
const supa = useSupabaseClient()

const Act = ('')

const getPengunjung = async () =>{
  const {error} = await supa
  .from('Tbl_LogActivity')
  .select('*')
  .order(`id`)
}

onMounted(() => {
  getPengunjung()
})
</script>

<style scoped>
.tbl {
    background-color: #83A0C3;
    box-shadow: 1px 1px 50px #83A0C3;
}
</style> -->