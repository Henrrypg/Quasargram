<template>
  <q-layout view="lHh Lpr lFf">
    <q-header
      class="bg-white text-grey-10"
      bordered
    >
      <q-toolbar class="constraint">
          <q-btn
          class="large-screen-only q-mr-sm"
          icon="eva-camera-outline"
          size="18px"
          to="/camera"
          flat
          round
          dense
          />
          <q-separator
            spaced
            vertical
            class="large-screen-only"
          />      
        <q-toolbar-title
          class="text-grand-hotel text-bold"
          >
          Quasargram
        </q-toolbar-title>
        <q-btn
          class="large-screen-only"
          icon="eva-home-outline"
          size="18px"
          to="/"
          flat
          round
          dense
          />
      </q-toolbar>
    </q-header>

    <q-footer
      class="bg-white small-screen-only"
      bordered
    >
          <q-tabs
            v-model="tab"
            class="text-grey-10"
            active-color="primary"
            indicator-color="transparent">
            <q-route-tab
              to="/"
              icon="eva-home-outline"
              name="Home"
            />            
            <q-route-tab
            to="/camera"
            icon="eva-camera-outline"
            name="Camera"
            />          
          </q-tabs>
    </q-footer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script lang="ts">


import { defineComponent, ref } from '@vue/composition-api';

export default defineComponent({
  name: 'MainLayout',
  data () {
    return {
      tab: 'mails'
    }
  }
});
</script>

<style lang="sass">
  .q-toolbar
    @media ( min-width:  $breakpoint-sm-min)
      height: 77px
  .q-footer
    .q-tab__icon
      font-size: 30px
  .q-toolbar__title
    @media ( max-width:  $breakpoint-xs-max)
      text-align: center
    font-size: 30px

</style>