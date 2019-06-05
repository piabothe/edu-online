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
              <v-card class="elevation-2" @click="select(n)">
                <v-card-title class="headline">Kapiteltitel</v-card-title>
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
  name: "courseoverview",
  props: {
    msg: String,
    module: String,
    course: String
  },
  data() {
    return {
      text: "Hier steht eine Kursbeschreibung samt grober Lernziele,"
    };
  },
  methods: {
    select: function(p) {
      if (this.module === "") {
        this.$emit("selectCourse", p);
      } else {
        this.$emit("selectChapter", p);
      }
    }
  }
};
</script>

<style>
</style>