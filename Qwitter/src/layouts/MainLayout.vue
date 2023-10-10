<template>
  <q-layout view="lHr lpR fFf">

    <q-header bordered class="bg-white text-black">
      <q-toolbar>
        <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" />

        <q-toolbar-title class="text-white-bold gt-md">
        Qwitter
        </q-toolbar-title>

        <q-icon 
        class="q-pa-md"
        name="fa-solid fa-dove"
        size="md"
        color="primary"
        />
        <!-- <q-btn dense flat round icon="menu" @click="toggleRightDrawer" /> -->
      </q-toolbar>
    </q-header>

    <q-drawer
      show-if-above
      v-model="leftDrawerOpen"
      side="left"
      :width="250"
      bordered>
      <q-icon 
      class="q-pa-md"
      name="fa-solid fa-dove"
      size="lg"
      color="primary"
      />
      <q-list>

      <q-item
        to="/"
        clickable
        v-ripple>
        <q-item-section avatar>
          <q-icon color="primary" name="home" />
        </q-item-section>

        <q-item-section class="text-h6 text-weight-bold">Home</q-item-section>
      </q-item>   
        <q-item
        to="/about"
          clickable
          v-ripple>
          <q-item-section avatar>
            <q-icon color="black" name="fa-solid fa-circle-question" />
          </q-item-section>          
          <q-item-section class="text-h6 text-weight-bold">About</q-item-section>
        </q-item>
  

    </q-list>
    </q-drawer>

    <q-drawer show-if-above v-model="rightDrawerOpen" side="right" bordered>

      <q-input
        placeholder="Search Quitter"
        outlined
        rounded
        dense
        class="q-ma-md">
        <template v-slot:prepend>
          <q-icon name="search" />
        </template>
      </q-input>

      <q-list
        separator
        padding>      
      <q-item class="q-pa-md">
        <q-item-section>
          <q-item-label overline class="text-grey">Politics</q-item-label>
          <q-item-label class="text-weight-bold">Its Happening Again!!</q-item-label>
          <q-item-label caption>Secondary line text. Lorem ipsum dolor sit amet, consectetur adipiscit elit.</q-item-label>
        </q-item-section>

        <q-item-section side top>
          <q-item-label caption>5 min ago</q-item-label>
        </q-item-section>
      </q-item>

      <q-item class="q-pa-md">
        <q-item-section>
          <q-item-label overline class="text-grey">Education</q-item-label>
          <q-item-label class="text-weight-bold">Kids are dumb</q-item-label>
          <q-item-label caption>Secondary line text. Lorem ipsum dolor sit amet, consectetur adipiscit elit.</q-item-label>
        </q-item-section>

        <q-item-section side top>
          <q-item-label caption>5 min ago</q-item-label>
        </q-item-section>
      </q-item> 
      
      <q-item class="q-pa-md">
        <q-item-section>
          <q-item-label overline class="text-grey">Arts & Literature</q-item-label>
          <q-item-label class="text-weight-bold">Showcase</q-item-label>
          <q-item-label caption>Secondary line text. Lorem ipsum dolor sit amet, consectetur adipiscit elit.</q-item-label>
        </q-item-section>

        <q-item-section side top>
          <q-item-label caption>5 min ago</q-item-label>
        </q-item-section>
      </q-item>
      </q-list>   
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

  </q-layout>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    const leftDrawerOpen = ref(false)
    const rightDrawerOpen = ref(false)

    return {
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      },

      rightDrawerOpen,
      toggleRightDrawer () {
        rightDrawerOpen.value = !rightDrawerOpen.value
      }
    }
  }
}
</script>