<template>
  <div>
    <Navbar></Navbar>
    <div class="container">
      <div class="row justify-content-center p-5">
        <div class="col-lg-3">
          <img src="~/assets/img/logo-apotek.png" alt="">
        </div>
      </div>
      <form @submit.prevent="log">
          <div class="mb-3">
                <label for="exampleInputEmail1" class="form-label">Email address</label>
                <input v-model="email" type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
          </div>
          <div class="mb-5">
                <label for="exampleInputPassword1" class="form-label">Password</label>
                <input v-model="password" type="password" class="form-control" id="exampleInputPassword1">
          </div>
        <div class="row justify-content-center">
          <div class="col-lg-1 ">
            <button class="btn btn-primary rounded-2 border-none" type="submit">Login</button>
          </div>
        </div>
      </form>
    </div>
  </div>
</template>
  
<script setup>
definePageMeta({
  layout: 'login'
})

const supa = useSupabaseClient()
const email = ref('')
const password = ref('')

async function log(){
  const {data,error} = await supa.auth.signInWithPassword({
    email: email.value,
    password: password.value,
  })

  if(data){
    navigateTo('/')
    const user = useSupabaseUser()
    insertLog(user)
  }
}

async function insertLog(user){
  const {error} = await supa
  .from('Tbl_LogActivity')
  .insert([{
    Aktivitas: 'Login',
    username: user.value.user_metadata.username,
    nama: user.value.user_metadata.username,
    tipe_user:user.value.user_metadata.tipe_user
  }])
}

</script>

<style>

.px {
  background-color: #83A0C3;
}
.ppp {
  font-size: 17px;
}

.height {
  height: 100px;
}

.pd {
  font-size: 1.5em;
}
img{
  width: 100%;

}

input{
  background-color: #D9D9D9 !important;
}
</style>