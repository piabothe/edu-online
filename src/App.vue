<template>
  <div id="app">
    <v-app id="inspire">
      <v-responsive>
        <v-layout xs12>
          <v-toolbar>
            <v-toolbar-title @click="changePage()">ABE Germany</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-toolbar-items class="hidden-sm-and-down">
              <v-btn flat @click="page = 'contact'">Kontakt</v-btn>
              <v-btn color="orange" v-show="login === 2" @click="logoutUser()">Logout</v-btn>
            </v-toolbar-items>
          </v-toolbar>
        </v-layout>

        <v-container>
          <v-layout align-center xs12 style="margin-top:20px">
            <v-flex>
              <h3 class="display-3">{{title}}</h3>
              <span class="subheading">{{text}}</span>
              <v-divider class="my-3"></v-divider>
              <div
                class="title mb-3"
                v-show="page === 'login'"
              >Neu hier? Registriere dich ganz ohne E-Mail-Adresse!</div>
              <v-alert
                :value="pwAlert"
                type="warning"
                v-show="login === 1 && pwAlert === true"
              >Das hat nicht funktioniert. Bitte verwende das Passwort aus den Unterlagen.</v-alert>
              <v-alert
                :value="userAlert"
                type="warning"
                v-show="login === 'login' && userAlert === true"
              >Das hat nicht funktioniert. Bitte wähle einen Benutzernamen.</v-alert>
              <p></p>

              <v-flex xs6>
                <v-card v-show="page === 'login'" @keyup.enter="loginUser()">
                  <div style="padding:20px">
                    <v-text-field label="Benutzername" v-model="user"></v-text-field>
                    <v-text-field label="Passwort" type="password" v-model="getpw"></v-text-field>

                    <v-btn color="#0065BD" large style="color: white" @click="loginUser()">Login</v-btn>
                    <v-btn color="#A2AD00" large>Registrieren</v-btn>
                  </div>
                </v-card>
              </v-flex>

              <Home v-show="page === 'home'" @selectModule="moduleSelected()"/>
              <ModuleOverview
                v-show="page === 'moduleOverview'"
                :module="selected_module"
                @selectCourse="courseSelected()"
              />
              <CourseOverview
                v-show="page === 'courseOverview'"
                :course="selected_course"
                @selectChapter="chapterSelected()"
              />
              <Chapter v-show="page === 'chapter'" :chapter="selected_chapter"/>
              <Contact v-show="page === 'contact'"/>
              <Impressum v-show="page === 'impressum'"/>
            </v-flex>
          </v-layout>
        </v-container>

        <v-footer class="footer" color="#0065BD" style="color:white">
          <v-spacer></v-spacer>
          <v-btn flat @click="page = 'impressum'" style="color:white">Impressum</v-btn>
          <div>&copy; {{ new Date().getFullYear() }}</div>
          <v-spacer></v-spacer>
        </v-footer>
      </v-responsive>
    </v-app>
  </div>
</template>

<script>
import Home from "./components/Home";
import Impressum from "./components/Impressum";
import ModuleOverview from "./components/ModuleOverview";
import CourseOverview from "./components/CourseOverview";
import Chapter from "./components/Chapter";
import Contact from "./components/Contact";

export default {
  name: "App",
  components: {
    CourseOverview: CourseOverview,
    Chapter: Chapter,
    Contact: Contact,
    Home: Home,
    Impressum: Impressum,
    ModuleOverview: ModuleOverview
  },
  data() {
    return {
      pwAlert: false,
      userAlert: false,
      getpw: "",
      login: 0,
      selected_chapter: "",
      selected_course: "",
      selected_module: "",
      setpw: "ABE2017",
      page: "login",
      text:
        "Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.",
      title: "Willkommen!",
      user: ""
    };
  },
  methods: {
    changePage: function() {
      if (this.login === 2) {
        this.page = "home";
      } else {
        this.page = "login";
      }
    },
    chapterSelected: function(param) {
      this.selected_chapter = param;
      this.page = "chapter";
    },
    courseSelected: function(param) {
      this.selected_course = param;
      this.page = "courseOverview";
    },
    loginUser: function() {
      this.userAlert = false;
      this.pwAlert = false;
      if (this.user === "") {
        this.userAlert = true;
        this.login = 1;
      } else {
        if (this.getpw === this.setpw) {
          this.page = "home";
          this.login = 2;
          this.title = "Hallo " + this.user + "!";
        } else {
          this.pwAlert = true;
          this.login = 1;
        }
      }
    },
    logoutUser: function() {
      this.page = "login";
      this.user = "";
      this.getpw = "";
      this.selected_chapter = "";
      this.selected_course = "";
      this.selected_module = "";
    },
    moduleSelected: function(param) {
      this.selected_module = param;
      this.page = "moduleOverview";
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
.footer {
  position: absolute;
  right: 0;
  bottom: 0;
  left: 0;
  padding: 1rem;
  background-color: #efefef;
  text-align: center;
}
</style>
