<template>
  <HeaderSection/>
  <ProfileSection/>
  <NavBar/>
</template>
<script setup>
import HeaderSection from './components/HeaderSection.vue'
import ProfileSection from './components/ProfileSection/ProfileSection.vue'
import NavBar from './components/NavBar.vue'
import { onMounted } from 'vue'
onMounted(() => {
  let el = document.querySelector('body')
  let h = el.offsetHeight
  if(el.offsetWidth < 576){
    el.style.height = +h + +(h*0.5) + 'px'
    console.log(el.offsetHeight)
  }else if(el.offsetWidth < 1199){
    el.style.height = +h + +200 + 'px'
  }else{
    el.style.height = +h + +(h*0.25) + 'px'
  }
})
</script>
<style scoped>

</style>