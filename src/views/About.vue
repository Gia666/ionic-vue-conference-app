<template>
<div class="ion-page">
  <ion-header>
    <ion-toolbar color="primary">
      <ion-buttons slot="start">
        <ion-menu-button></ion-menu-button>
      </ion-buttons>
      <ion-title>About</ion-title>
      <ion-buttons slot="end">
        <ion-button @click="presentPopover($event)">
          <ion-icon slot="icon-only" name="more"></ion-icon>
        </ion-button>
      </ion-buttons>
    </ion-toolbar>
  </ion-header>

  <ion-content>
    <div class="about-header">
      <img src="/assets/img/ionic-logo-white.svg" alt="ionic logo">
    </div>
    <div padding class="about-info">
      <h4>Ionic Conference</h4>

      <ion-list lines="none">
        <ion-item>
          <ion-icon name="calendar" slot="start"></ion-icon>
          <ion-label>Date</ion-label>
          <ion-datetime displayFormat="MMM DD, YYYY" max="2056" :value="conferenceStart"></ion-datetime>
        </ion-item>

        <ion-item>
          <ion-icon name="pin" slot="start"></ion-icon>
          <ion-label>Location</ion-label>
          <ion-select>
            <ion-select-option value="madison" selected>Madison, WI</ion-select-option>
            <ion-select-option value="austin">Austin, TX</ion-select-option>
            <ion-select-option value="chicago">Chicago, IL</ion-select-option>
            <ion-select-option value="seattle">Seattle, WA</ion-select-option>
          </ion-select>
        </ion-item>
      </ion-list>

      <p>
        The Ionic Conference is a one-day conference featuring talks from the Ionic team. It is focused on Ionic applications being built with Ionic 2. This includes migrating apps from Ionic 1 to Ionic 2, Angular concepts, Webpack, Sass, and many other technologies
        used in Ionic 2. Tickets are completely sold out, and we’re expecting more than 1000 developers – making this the largest Ionic conference ever!
      </p>
    </div>
  </ion-content>
</div>
</template>

<script lang="ts">
  import { Component, Prop, Vue } from 'vue-property-decorator';
  import { mapGetters } from 'vuex';

  @Component({
    computed: mapGetters(['conferenceStart'])
  })
  export default class About extends Vue {

    presentPopover(){
      //console.log('click', event)
    }
  }
</script>

<style scoped>
.about-header {
  background-color: #434954;
  padding: 16px;
  width: 100%;
  min-height: 150px;
  text-align: center;
}

.about-header img {
  max-width: 200px;
  min-height: 115px;
  margin-left: -15px;
  padding: 25px 0 20px 0;
}

.about-info p {
  color: #697072;
  text-align: left;
}

.about-info ion-icon {
  width: 20px;
}

.md .about-info [text-right],
.wp .about-info [text-right] {
  margin-right: 0;
}

.ios .about-info {
  text-align: center;
}

.ios .about-info ion-icon {
  width: auto;
  margin-right: 10px;
}
</style>
