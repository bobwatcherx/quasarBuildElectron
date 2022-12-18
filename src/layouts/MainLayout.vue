<script setup>
   function minimize () {
      if (process.env.MODE === 'electron') {
        window.myWindowAPI.minimize()
      }
    }

    function toggleMaximize () {
      if (process.env.MODE === 'electron') {
        window.myWindowAPI.toggleMaximize()
      }
    }

    function closeApp () {
      if (process.env.MODE === 'electron') {
        window.myWindowAPI.close()
      }
    }
</script>
<template>
  <q-layout>
     <q-header elevated class="bg-black ">
    <q-bar class="q-electron-drag bg-primary fixed-top shadow-5 text-white text-bold " style="height:50px">
  <q-icon name="map" class="q-electron-drag--exception" />
<span class="q-ml-md text-h5 text-bold">McDonald's App</span>

<q-space/>
    <q-btn dense flat icon="minimize" @click="minimize" />
          <q-btn dense flat icon="crop_square" @click="toggleMaximize" />
          <q-btn dense flat icon="close" @click="closeApp" />
</q-bar>
</q-header>
    <q-page-container>
      <router-view/>
    </q-page-container>
  </q-layout>
</template>