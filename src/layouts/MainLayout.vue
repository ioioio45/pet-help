
<template>
  <q-layout view="lHh Lpr lFf">
    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <q-item-label
          header
        >
        </q-item-label>

        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>
    <q-footer bordered class="bg-white text-primary  justify-evenly" style="width: 100vw; padding: 0" reveal:false>
        <q-tabs no-caps indicator-color="transparent" class="text-grey justify-evenly" v-model="tab">
          <q-tab name="images" style="width: 50px">
            <q-btn
              :icon="$q.platform.is.ios ? 'settings' : 'ion-ios-gear-outline'"
            />
          </q-tab>
          <q-tab name="videos" style="width: 50px">
            <q-btn
              :icon="$q.platform.is.ios ? 'settings' : 'ion-ios-gear-outline'"
            />
          </q-tab>
          <q-tab name="articles" style="width: 50px">
            <q-btn
              :icon="$q.platform.is.ios ? 'settings' : 'ion-ios-gear-outline'"
            />
          </q-tab>
        </q-tabs>
      </q-footer>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>
<link href="https://vjs.zencdn.net/8.0.4/video-js.css" rel="stylesheet" />
<script>
import { defineComponent, ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
  {
    title: 'Профиль',
    icon: 'school',
    link: '../#/Profile'
  },
  {
    title: 'Загрузить видео',
    icon: 'school',
    link: 'https://quasar.dev'
  }
]

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>
<style>
  q-tab {
    width: 50px;
  }
</style>
