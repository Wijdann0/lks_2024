<template>
    <div class="container">
          <div class="row pt-5">
              <div class="col-lg-8 d-flex justify-content-center">
              <h2>Riwayat Transaksi</h2>
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
                        <th scope="col">No Transaksi</th>
                        <th scope="col">Tgl Transaksi</th>
                        <th scope="col">Id user</th>
                        <th scope="col">Id Obat</th>
                        <th scope="col">Id Resep</th>
                        <th scope="col">Quantity</th>
                        <th scope="col">Total Bayar</th>
                      </tr>
                    </thead>
                    <tbody>
                      <tr>
                        <th scope="row">1</th>
                        <td>Mark</td>
                        <td>Otto</td>
                        <td>@mdo</td>
                        <td>@mdo</td>
                        <td>@mdo</td>
                        <td>@mdo</td>
                      </tr>
                      <tr>
                        <th scope="row">2</th>
                        <td>Jacob</td>
                        <td>Thornton</td>
                        <td>@fat</td>
                        <td>@fat</td>
                        <td>@fat</td>
                        <td>@fat</td>
                      </tr>
                      <tr>
                        <th scope="row">3</th>
                        <td>Larry the Bird</td>
                        <td>@twitter</td>
                        <td>@twitter</td>
                        <td>@twitter</td>
                        <td>@twitter</td>
                        <td>@twitter</td>
                      </tr>
                      <tr>
                        <th scope="row">3</th>
                        <td>Larry the Bird</td>
                        <td>@twitter</td>
                        <td>@twitter</td>
                        <td>@twitter</td>
                        <td>@twitter</td>
                        <td>@twitter</td>
                      </tr>
                      <tr>
                      <th scope="row">3</th>
                      <td>Larry the Bird</td>
                      <td>@twitter</td>
                      <td>@twitter</td>
                      <td>@twitter</td>
                      <td>@twitter</td>
                      <td>@twitter</td>
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
  