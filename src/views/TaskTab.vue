<template>
  <ion-page>

    <div id="container">
        <TaskOverview />
    </div>

  </ion-page>
</template>

<script lang="js">
import { defineComponent } from 'vue';
import { IonPage } from '@ionic/vue';
import TaskOverview from '/src/components/TabViews/TaskOverview.vue'

export default  defineComponent({
  name: 'Tab1Page',
  components: { IonPage, TaskOverview }
});
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
