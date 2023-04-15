<script setup lang="ts">
import TheWelcome from '../components/TheWelcome.vue'
import axios from 'axios'

axios.post("/api/auth/login",{
  username:'xiaoc',
  password:'999999'
}).then(res=>{
  console.log("------------res-----------")
  console.log(res)

  axios.get('/api/user', {
    headers:{
      'Authorization': 'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InhpYW9jIiwic3ViIjo3LCJpYXQiOjE2NzgxNjMyNjQsImV4cCI6MTY3ODE2Mzg2NH0.Fxd6JJpnmo4g3IK6vCkMw40pRTjqpylpj6NiLVPsFsA'
    }
  }).then(res=>{
    console.log('------user list----------')
    console.log(res);
  })
})
</script>

<template>
  <main>
    <TheWelcome />
  </main>
</template>
