<template>
  <div>
    <v-container>
      <v-layout align-center>
        <v-flex>
          <h3 class="display-3">{{title}}</h3>
          <v-divider class="my-3"></v-divider>

          <v-layout xs12>
            <v-flex xs6>
              <v-btn color="primary">Zurück</v-btn>
            </v-flex>
            <v-flex xs6>
              <v-btn color="primary">Weiter</v-btn>
            </v-flex>
            <p></p>
          </v-layout>

          <v-card>
            <v-card-text>
              <img v-if="hover" height="100 px" src="../assets/pic.jpg">
              <p>
                Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut,
                sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus,
                vix an salutandi sententiae. Lorem ipsum dolor sit amet, no nam
                <v-tooltip right>
                  <template v-slot:activator="{ on }">
                    <v-btn color="primary" style="font-weight:bold" small flat v-on="on">oblique</v-btn>
                  </template>
                  <span>seitliche Bauchmuskulatur</span>
                </v-tooltip>veritus. Commune scaevola imperdiet nec ut,
                sed euismod convenire
                <b>principes</b> at. Est et nobis iisque percipit, an vim zril disputando voluptatibus,
                vix an salutandi sententiae. Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut,
                sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril
                <b>disputando</b> voluptatibus,
                vix an salutandi sententiae.
              </p>
              <p>
                Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut,
                sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus,
                vix an salutandi sententiae. Lorem ipsum dolor sit amet, no nam
                <b>oblique</b> veritus. Commune scaevola imperdiet nec ut,
                sed euismod convenire
                <b>principes</b> at. Est et nobis iisque percipit, an vim zril disputando voluptatibus,
                vix an salutandi sententiae. Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut,
                sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril
                <b>disputando</b> voluptatibus,
                vix an salutandi sententiae.
              </p>
            </v-card-text>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
export default {
  name: "chapter",
  props: {},
  data() {
    return {
      title: "Das Alignment",
      hover: false
    };
  }
};
</script>

<style>
</style>