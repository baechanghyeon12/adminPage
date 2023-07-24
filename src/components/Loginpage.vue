<template>
    <div>
        <form>
            <p>
                <label for="admin_id">ID</label>
                <input type="text" id="admin_id" v-model.trim="$store.state.AdminId" autocomplete="username">
            </p>
            <p>
                <label for="admin_pw">PW</label>
                <input type="password" id="admin_pw" v-model.trim="$store.state.AdminPw" autocomplete="current-password">
            </p>
        </form>
        <button @click="$store.dispatch('adminLoginCheck')">Login</button>
    </div>
</template>
<script>
export default {
    name: 'Loginpage',
}
</script>
<style>
    
</style>