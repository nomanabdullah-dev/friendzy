<template>
   <div class="bg-blue-500 text-white text-md">
      <nav class="container flex justify-between items-center mx-auto py-5">
         <span class="font-semibold text-2xl tracking-wide">Friendzy</span>
         <div class="space-x-2">
            <template v-if="this.$auth.loggedIn">
               <span>Welcome,
                  <nuxt-link to="#" class="capitalize hover:text-blue-200">{{ this.$auth.user.username }}</nuxt-link>
               </span>
               <nuxt-link to="/friends" class="hover:text-blue-200">FRIENDS</nuxt-link>
               <nuxt-link to="/users" class="hover:text-blue-200">USERS</nuxt-link>
               <nuxt-link to="/dashboard" class="hover:text-blue-200">DASHBOARD</nuxt-link>
               <a href="#" @click.prevent="logout" class="hover:text-blue-200">LOGOUT</a>
            </template>
            <template v-else>
               <nuxt-link to="/auth/register" class="hover:text-blue-200">REGISTER</nuxt-link>
               <nuxt-link to="/auth/login" class="hover:text-blue-200">LOGIN</nuxt-link>
            </template>
         </div>
      </nav>
   </div>
</template>

<script>
export default {
   methods: {
      logout() {
         this.$auth.logout()
      }
   },
}
</script>
