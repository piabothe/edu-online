<template>
  <div>
    <v-container>
      <v-layout align-center xs12>
        <v-flex>
          <h3 class="display-3">Kursbereiche</h3>
          <v-divider class="my-3"></v-divider>

          <v-card class="elevation-2" @click="selectModule('BI')">
            <v-card-title class="headline">Grundlagen der Bioinformatik</v-card-title>
            <v-card-text>Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.</v-card-text>
          </v-card>

          <p></p>

          <v-card class="elevation-2" style="color:darkgrey">
            <v-card-title class="headline">Grundlagen der Informatik</v-card-title>
            <v-card-text>Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.</v-card-text>
          </v-card>

          <p></p>

          <v-card class="elevation-2" style="color:darkgrey">
            <v-card-title class="headline">Grundlagen der Molekularbiologie</v-card-title>
            <v-card-text>Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.</v-card-text>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
export default {
  name: "home",
  props: {},
  data() {
    return {};
  },
  methods: {
    selectModule: function(p) {
      this.$emit("selectModule", "BI");
    }
  }
};
</script>

<style>
</style>