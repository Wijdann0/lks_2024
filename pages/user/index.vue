<template>
  <div class="container">
        <div class="row pt-5">
            <div class="col-lg-8 d-flex justify-content-center">
            <h2>Data User</h2>
        </div>
        <div class="col-lg-1 d-flex justify-content-center">
            <nuxt-link to="/user/tambah">
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
                      <th scope="col">username</th>
                      <th scope="col">tipe user</th>
                      <th scope="col">email</th>
                    </tr>
                  </thead>
                  <tbody>
                    <tr>
                      <th scope="row">1</th>
                      <td>Mark</td>
                      <td>Otto</td>
                      <td>@mdo</td>
                    </tr>
                  </tbody>
                </table>
          </div>
        </div>
      </div>
</template>
      
<script setup>

</script>

<style scoped>
.tbl {
    background-color: #83A0C3;
    box-shadow: 1px 1px 50px #83A0C3;
}
</style>
