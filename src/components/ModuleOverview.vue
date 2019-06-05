<template>
  <div>
    <v-container>
      <v-layout align-center>
        <v-flex>
          <h3 class="display-3">{{module}}</h3>
          <span class="subheading">{{text}}</span>
          <v-divider class="my-3"></v-divider>

          <v-timeline>
            <v-timeline-item v-for="n in 4" :key="n" color="#0065BD" large>
              <v-card class="elevation-2" @click="selectCourse(n)">
                <v-card-title class="headline">Kurstitel</v-card-title>
                <v-card-text>Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.</v-card-text>
              </v-card>
            </v-timeline-item>
          </v-timeline>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
export default {
  name: "moduleoverview",
  props: {
    msg: String,
    module: String
  },
  data() {
    return {
      text:
        "Hier steht eine Modulbeschreibung + Anforderung + weiterführende Informationen."
    };
  },
  methods: {
    selectCourse: function(p) {
      this.$emit("selectCourse", p);
    }
  }
};
</script>

<style>
</style>