<template>

<div id="container">
    
    <ion-content :fullscreen="true">
    
      <ion-grid>
        <ion-row class="ion-align-items-center">
          <ion-col col-6 class="task_img">
              <div @click="fetchInspections">
                <div>
                  <ion-icon src="./assets/icon/tasks.svg"></ion-icon>
                  <p>Assigned inspections</p>
                </div>
              </div>
          </ion-col>
          <ion-col col-6 class="task_img">
            <div @click="fetchReports">
              <ion-icon src="../assets/icon/completed.svg"></ion-icon>
              <p>Finished Reports</p>
            </div>
          </ion-col>
        </ion-row>

        <ion-row>
          <ion-col col-6 class="task_img">
            <div @click="fetchKnowledge">
              <ion-icon src="../assets/icon/knowledge.svg"></ion-icon>
              <p>knowledge base</p>
            </div>
          </ion-col>
          <ion-col col-6 class="task_img">
            <div @click="fetchSettings">
              <ion-icon src="../assets/icon/settings.svg"></ion-icon>
              <p>Settings</p>
            </div>
          </ion-col>
        </ion-row>
      </ion-grid>

    </ion-content>
    </div>
</template>

<script lang="js">
import { defineComponent } from 'vue';
import { IonContent, modalController, IonGrid, IonCol, IonRow, IonIcon } from '@ionic/vue';
import mixins from '/src/mixins/mixins.js'
import InspectionStore from "../Inspections/InspectionStore"
import FinishedReports from "../Inspections/FinishedReports"
import KnowledgeBase from "../Knowledge//KnowledgeBase"
import SettingsOverview from "../Settings/SettingsOverview"

export default  defineComponent({
  name: 'TaskOverview',
  components: { IonContent, IonGrid, IonCol, IonRow, IonIcon  },
  mixins: [mixins],
  methods: {
    async fetchInspections() {
      const modal = await modalController
        .create({
          component: InspectionStore,
          cssClass: 'inspections-class'
        })
      this.$router.push("/tabs/tab1/Assigned-reports")
      return modal.present();
    },
    async fetchReports() {
      const modal = await modalController
        .create({
          component: FinishedReports,
          cssClass: 'reports-class'
        })
      this.$router.push("/tabs/tab1/Finished-reports")
      return modal.present();
    },
    async fetchKnowledge() {
      const modal = await modalController
        .create({
          component: KnowledgeBase,
          cssClass: 'knowledge-class'
        })
      this.$router.push("/tabs/tab1/Knowledge-base")
      return modal.present();
    },
    async fetchSettings() {
      const modal = await modalController
        .create({
          component: SettingsOverview,
          cssClass: 'settings-class'
        })
      this.$router.push("/tabs/tab1/Settings")
      return modal.present();
    },
  },
})
</script>

<style scoped>

  ion-icon{
    font-size: 100px !important;
    color: rgb(35, 35, 35);
  }

  .task_img{
    margin: 10px !important;
    cursor: pointer;
  }

  ion-col{
    box-shadow: 0px 2px 6px gray;
    border-radius: 5px;
    text-align: center;
  }
</style>