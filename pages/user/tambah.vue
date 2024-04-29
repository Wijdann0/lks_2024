<template>
    <div class="container">
    <div class="row container justify-content-center pt-5 pb-5">
        <div class="col-lg-8">
            <h2>Kelola User</h2>
        </div>
    </div>
    <form @submit.prevent="tambahUser">
        <div class="row justify-content-around pb-4">
            <div class="col-lg-4">
                <select v-model="tipe" class="form-control form-control-lg form-select rounded-3 input">
                    <option value="" disabled>Tipe user</option>
                    <option>Admin</option>
                    <option>Apoteker</option>
                    <option>Kasir</option>
                </select>
                <!-- <input v-model="tipe" class="form-control" type="text" placeholder="Tipe User" aria-label="default input example"> -->
            </div>

            <div class="col-lg-4">
                <input v-model="username" class="form-control" type="text" placeholder="Username" aria-label="default input example">
            </div>
        </div>
        <div class="row justify-content-around pb-4">
            <div class="col-lg-4">
                <input v-model="email" class="form-control" type="text" placeholder="Email" aria-label="default input example">
            </div>

            <div class="col-lg-4">
                <input v-model="password" class="form-control" type="text" placeholder="Password" aria-label="default input example">
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
            <nuxt-link to="/user">
                <button class="btn btn-light" type="submit">Data User</button>
            </nuxt-link>
        </div>
    </div>
</div>
</template>

<script setup>
const supa = useSupabaseClient()

const tipe = ref('')
const username = ref('')
const email = ref('')
const password = ref('')

async function tambahUser (){
    const {data,error} = await supa.auth.signUp({
        email: email.value,
        password: password.value,
        options:{
            data:{
                username: username.value,
                tipe: tipe.value,
            }
        }
    })
    if(data){
        const {error} = await supa.auth.signOut()
        navigateTo('/')
    }
}
</script>

<style>

input{
    background-color: #D9D9D9 !important;
}

.input{
    background-color: #D9D9D9 !important;
}
</style>