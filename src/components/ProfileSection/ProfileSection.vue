<template>
    <section>
        <div class="container">
            <ProfileInfo :user="user"/>
            <ProfileContent :user="user"/>
        </div>
    </section>
</template>
<script setup>
import axios from 'axios'
import { ref , onMounted} from 'vue'
import ProfileContent from './ProfileContent.vue'
import ProfileInfo from './ProfileInfo.vue'
let user = ref({})
onMounted(async()=>{
  await axios.get('https://ybiapi.fresh-app.com/api/demo_profile')
  .then(res => {
    user.value = res.data
  })
  .catch(console.error())
})
</script>
<style scoped>
section .container{
  display: flex;
  flex-wrap: wrap;
  gap: 5%;
}
</style>