<template>
  <q-layout view="lHh Lpr lFf">
       <q-card>
        <q-tabs
          v-model="tab"
          class="text-teal"
        >
          <q-tab name="dashboard"  label="Dashboard" />
          <q-tab name="graph" label="Graph" />
          <q-tab name="detail" label="Detail" />
        </q-tabs>
          <q-separator />

      </q-card>


    <q-page-container>
          <q-tab-panels v-model="tab" animated>
            <q-tab-panel name="dashboard">
                <dashboard />
            </q-tab-panel>

            <q-tab-panel name="graph">
              <div class="text-h6">Alarms</div>
              Lorem ipsum dolor sit amet consectetur adipisicing elit.
            </q-tab-panel>

            <q-tab-panel name="detail">
              <detail />
            </q-tab-panel>
          </q-tab-panels>
    </q-page-container>
  </q-layout>
</template>

<script>


import { ref } from 'vue'

export default {
  setup () {
    return {
      tab: ref('dashboard')
    }
  },
  components: {
    'dashboard': require('pages/Dashboard.vue').default,
    'detail': require('pages/Detail.vue').default,
    
  }
}
</script>
