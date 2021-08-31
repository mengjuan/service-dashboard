<template>
  <q-page class="flex column">
   <q-form dense>
      <div class="row q-pa-md" dense >
        <q-input dense filled v-model="date" mask="date" :rules="['date']">
          <template v-slot:append>
            <q-icon  name="event" class="cursor-pointer">
              <q-popup-proxy ref="qDateProxy" transition-show="scale" transition-hide="scale">
                <q-date  v-model="date">
                  <div class="row items-center justify-end">
                    <q-btn  v-close-popup label="Close" color="primary" flat />
                  </div>
                </q-date>
              </q-popup-proxy>
            </q-icon>
          </template>
        </q-input>
        <div >
          <q-btn  color="primary" label="Query" />
      </div>
    </div>
    </q-form>
     <div class="q-pa-md row items-start q-gutter-md q-b shadow-1">
      <q-card class="my-card bg-primary text-white">
        <q-card-section>
          <div class="text-h6">Serivce</div>
        </q-card-section>
        <q-separator dark />
        <q-card-actions>
          <q-btn flat>130</q-btn>
          <q-btn flat class="text-red">3</q-btn>
        </q-card-actions>
      </q-card>
    
      <q-card class="my-card bg-primary text-white">
        <q-card-section>
          <div class="text-h6">Request</div>
        </q-card-section>
        <q-separator dark />
        <q-card-actions>
          <q-btn flat>145530</q-btn>
          <q-btn flat class="text-red">332</q-btn>
        </q-card-actions>
      </q-card>
       <q-card class="my-card bg-primary text-white">
        <q-card-section>
          <div class="text-h6">Performance</div>
          <div class="text-subtitle2">0.592s</div>
        </q-card-section>
        <q-separator dark />
        <q-card-actions>
              <q-dialog v-model="card">
                <div class="q-pa-md row items-start q-gutter-md">
                    <q-card class="my-card bg-primary text-white">
                      <q-card-section>
                        <div class="text-h6">US</div>
                      </q-card-section>
                      <q-separator dark />
                      <q-card-actions>
                        <div class="text-h8">300(>5s)</div>
                        <div class="text-h8">23(>10s)</div>
                      </q-card-actions>
                    </q-card>
                    <q-card class="my-card bg-primary text-white">
                      <q-card-section>
                        <div class="text-h6">HYVE US</div>
                      </q-card-section>
                      <q-separator dark />
                      <q-card-actions>
                        <div class="text-h8">300(>5s)</div>
                        <div class="text-h8">23(>10s)</div>
                      </q-card-actions>
                    </q-card>
                  </div>
              </q-dialog>
          <q-btn flat @click="card=true">145530(>5s)</q-btn>
          <q-btn flat class="text-red">332(>10s)</q-btn>
        </q-card-actions>
      </q-card>
       <q-card class="my-card bg-primary text-white">
        <q-card-section>
          <div class="text-h6">Error</div>
        </q-card-section>
        <q-separator dark />
        <q-card-actions>
          <q-btn flat class="text-red">26</q-btn>
        </q-card-actions>
      </q-card>

      <q-card class="my-card bg-primary text-white">
        <q-card-section>
          <div class="text-h6">User</div>
        </q-card-section>
        <q-separator dark />
        <q-card-actions>
          <q-btn flat>156777</q-btn>
          <q-btn flat class="text-green">578</q-btn>
        </q-card-actions>
      </q-card>
       <q-card class="my-card bg-primary text-white">
        <q-card-section>
          <div class="text-h6">CPU(cores)</div>
        </q-card-section>
        <q-separator dark />
        <q-card-actions>
          <q-btn flat>200</q-btn>
          <q-btn flat class="text-red">8</q-btn>
        </q-card-actions>
      </q-card>

       <q-card class="my-card bg-primary text-white">
        <q-card-section>
          <div class="text-h6">Memory(GB)</div>
        </q-card-section>
        <q-separator dark />
        <q-card-actions>
          <q-btn flat>200</q-btn>
          <q-btn flat class="text-red">10</q-btn>
        </q-card-actions>
      </q-card>
      <q-card class="my-card bg-primary text-white">
        <q-card-section>
          <div class="text-h6">Code Quality</div>
        </q-card-section>
        <q-separator dark />
        <q-card-actions>
          <q-btn flat>145</q-btn>
          <q-btn flat class="text-red">10(coverage less 80%)</q-btn>
        </q-card-actions>
      </q-card>
      <q-card class="my-card bg-primary text-white">
        <q-card-section>
          <div class="text-h6">Build</div>
        </q-card-section>
        <q-separator dark />
        <q-card-actions>
          <q-btn flat>145</q-btn>
          <q-btn flat class="text-red">23</q-btn>
        </q-card-actions>
      </q-card>
      <q-card class="my-card bg-primary text-white">
        <q-card-section>
          <div class="text-h6">Release</div>
        </q-card-section>
        <q-separator dark />
        <q-card-actions>
          <q-btn flat>145</q-btn>
        </q-card-actions>
      </q-card>
      <q-card class="my-card bg-primary text-white">
        <q-card-section>
          <div class="text-h6">Jira Issue</div>
        </q-card-section>
        <q-separator dark />
        <q-card-actions>
          <q-btn flat>145</q-btn>
        </q-card-actions>
      </q-card>
    </div>

    <div class="row q-col-gutter-sm q-ml-xs q-mr-sm q-py-sm">
      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <line-chart></line-chart>
      </div>
      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <bar-chart></bar-chart>
      </div>
      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <pie-chart></pie-chart>
      </div>
      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <scatter-chart></scatter-chart>
      </div>
      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <dotted-bar-chart></dotted-bar-chart>
      </div>
      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <guage-chart></guage-chart>
      </div>
      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <boxplot></boxplot>
      </div>
      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <area-chart></area-chart>
      </div>
    </div>
 

  </q-page>
</template>

<script>
import { defineComponent } from 'vue';
import { ref } from 'vue'
import LineChart from "components/LineChart";
import BarChart from "components/BarChart";
import PieChart from "components/PieChart";
import ScatterChart from "components/ScatterChart";
import DottedBarChart from "components/DottedBarChart";
import GuageChart from "components/GuageChart";
import Boxplot from "components/BoxChart";
import AreaChart from "components/AreaChart";

export default defineComponent({
  data(){
    return {
      serviceName: "",
      date:ref('2019/02/01'),
      card: ref(false),
    }
  },
  components: {AreaChart, Boxplot, GuageChart, DottedBarChart, ScatterChart, PieChart, BarChart, LineChart}
  
})
</script>
