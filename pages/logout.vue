<template>
    <div class="container">
        <h1>Sedang Keluar</h1>
    </div>
</template>
  
<script setup>
const supa = useSupabaseClient()
  
async function keluar(){
const{error} = await supa.auth.signOut()
if(!error) navigateTo('/login')
}

async function insertLog(){
    const  user = useSupabaseUser()
    const {error} = await supa
    .from('Tbl_LogActivity')
    .insert([{
        Aktivitas: 'Logout',
        username: user.value.user_metadata.username,
        nama: user.value.user_metadata.username,
        tipe_user: user.value.user_metadata.tipe_user,
    }])
    if(!error) keluar()
}

onMounted (() => {
insertLog()
})
  
</script>

<style>

</style>