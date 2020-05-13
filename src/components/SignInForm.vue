<template>
  <v-app class="container" style="margin-top: 200px">
    <v-stepper v-model="e1" vertical>
      <!-- ---------
          PRVI KORAK
      ------------>
      <template>
        <v-stepper-step step="1" edit-icon="person" complete editable>Korisnički podaci</v-stepper-step>
        <v-stepper-content step="1">
          <v-form>
            <v-row>
              <v-col cols="12" md="6">
                <v-text-field
                  class="v-input__control"
                  v-model="imePrezime"
                  label="Ime i prezime"
                  append-icon="person"
                  :rules="textRules"
                  outlined
                  required
                ></v-text-field>
              </v-col>
              <v-col cols="12" md="6">
                <v-text-field
                  v-model="mjestoPrebivališta"
                  label="Mjesto prebivališta"
                  append-icon="house"
                  :rules="textRules"
                  outlined
                  required
                ></v-text-field>
              </v-col>
            </v-row>

            <v-row>
              <v-col cols="12" md="6">
                <v-text-field
                  v-model="JMBG"
                  label="JMBG"
                  :rules="textRules"
                  append-icon="vpn_key"
                  required
                  outlined
                ></v-text-field>
              </v-col>
              <v-spacer></v-spacer>
              <v-col cols="12" md="6">
                <v-menu
                  v-model="menu"
                  :close-on-content-click="false"
                  :nudge-right="40"
                  transition="scale-transition"
                  offset-y
                  min-width="290px"
                >
                  <template v-slot:activator="{ on }">
                    <v-text-field
                      v-model="datumRodenja"
                      label="Datum rođenja"
                      append-icon="event"
                      :rules="textRules"
                      outlined
                      readonly
                      v-on="on"
                    ></v-text-field>
                  </template>
                  <v-date-picker locale="hr" v-model="datumRodenja" @input="menu = false"></v-date-picker>
                </v-menu>
              </v-col>
              <v-spacer></v-spacer>
            </v-row>
            <v-row>
              <v-col cols="12" md="6">
                <v-text-field
                  class="v-input__control"
                  v-model="email"
                  label="Email"
                  :rules="emailRules"
                  append-icon="email"
                  outlined
                  required
                ></v-text-field>
              </v-col>
            </v-row>
          </v-form>

          <v-btn class="float-right" color="primary" rounded @click="nextStep(1)">
            <span class="buttonText">Dalje</span>
            <v-icon right>navigate_next</v-icon>
          </v-btn>
        </v-stepper-content>
      </template>
      <!-- ----------
          DRUGI KORAK
      ------------->
      <template>
        <v-stepper-step edit-icon="school" step="2" complete editable>Školovanje</v-stepper-step>
        <v-stepper-content step="2">
          <v-row>
            <v-col cols="12" md="6">
              <v-text-field
                class="v-input__control"
                v-model="srednjaSkola"
                label="Završena srednja škola"
                :rules="textRules"
                append-icon="school"
                required
                outlined
              ></v-text-field>
            </v-col>
            <v-col cols="12" md="6">
              <v-autocomplete
                :items="smjerovi"
                :filter="customFilter"
                item-text="name"
                label="Koji smjer fakulteta želite izabrati"
                append-icon="school"
                :rules="textRules"
                outlined
                required
              >
                <v-list-item-title></v-list-item-title>
              </v-autocomplete>
            </v-col>
          </v-row>

          <v-row>
            <v-col cols="12" md="6">
              <v-form ref="form" lazy-validation>
                <v-text-field v-model="imePrezime" label="Name" outlined required></v-text-field>
              </v-form>
            </v-col>
            <v-col cols="12" md="6">
              <v-autocomplete
                :items="smjerovi"
                :filter="customFilter"
                item-text="name"
                label="Koji smjer fakulteta želite izabrati"
                append-icon="school"
                :rules="textRules"
                outlined
                required
              >
                <v-list-item-title></v-list-item-title>
              </v-autocomplete>
            </v-col>
          </v-row>

          <v-btn class="float-left" color="primary" outlined rounded @click="back()">
            <v-icon left>navigate_before</v-icon>
            <span class="buttonText">Natrag</span>
          </v-btn>

          <v-btn class="float-right" color="primary" rounded @click="nextStep(2)">
            <span class="buttonText">Dalje</span>
            <v-icon right>navigate_next</v-icon>
          </v-btn>
        </v-stepper-content>
      </template>
      <!-- ---------
          TREĆI KORAK
      ------------>
      <template>
        <v-stepper-step
          ref="stepper-step"
          id="nesto"
          edit-icon="person"
          step="3"
          complete
          editable
        >Korisnički podaci</v-stepper-step>
        <v-stepper-content step="3">
          <v-form>
            <v-row>
              <v-col cols="12" md="6">
                <v-text-field
                  class="v-input__control"
                  v-model="imePrezime"
                  label="Ime i prezime"
                  append-icon="person"
                  :rules="textRules"
                  outlined
                  required
                ></v-text-field>
              </v-col>
              <v-col cols="12" md="6">
                <v-text-field
                  v-model="mjestoPrebivališta"
                  label="Mjesto prebivališta"
                  append-icon="house"
                  :rules="textRules"
                  outlined
                  required
                ></v-text-field>
              </v-col>
            </v-row>
          </v-form>

          <v-btn class="float-left" color="primary" outlined rounded @click="back()">
            <v-icon left>navigate_before</v-icon>
            <span class="buttonText">Natrag</span>
          </v-btn>

          <v-btn class="float-right" color="primary" rounded @click="nextStep(3)">
            <span class="buttonText">Dalje</span>
            <v-icon right>navigate_next</v-icon>
          </v-btn>
        </v-stepper-content>
      </template>
      <!-- ------------
          ČETVRTI KORAK
      --------------->
      <template>
        <v-stepper-step step="4" edit-icon="check" complete editable>Kraj</v-stepper-step>
        <v-stepper-content step="4">
          <v-snackbar color="success" v-model="successSnackbar" bottom>
            Podaci uspješno poslani.
            Hvala na prijavi
            <v-btn text @click="successSnackbar = false">Zatvori</v-btn>
          </v-snackbar>

          <v-snackbar color="error" v-model="errorSnackbar" bottom>
            Došlo je do pogreške. Pokušajte ponovno
            <v-btn text @click="errorSnackbar = false">Zatvori</v-btn>
          </v-snackbar>

          <v-btn class="float-left" color="primary" outlined rounded @click="back()">
            <v-icon left>navigate_before</v-icon>
            <span class="buttonText">Natrag</span>
          </v-btn>

          <v-btn color="orange darken-1" rounded class="float-right" @click="sendData()">
            <span class="buttonText">Pošalji</span>
            <v-icon right>backup</v-icon>
          </v-btn>
        </v-stepper-content>
      </template>
    </v-stepper>
  </v-app>
</template>

<script>
export default {
  name: "HelloWorld",

  data: () => ({
    e1: 1,
    steps: 4,
    menu: false,
    successfullySent: false,
    successSnackbar: false,
    errorSnackbar: false,
    datumRodenja: new Date().toISOString().substr(0, 10),
    imePrezime: "",
    time: "",
    JMBG: "",
    mjestoPrebivališta: "",
    srednjaSkola: "",
    smjer: "",
    textRules: [v => !!v || "Obavezno polje"],
    email: "",
    emailRules: [
      v => !!v || "Obavezno polje",
      v => /.+@.+/.test(v) || "Pogrešan format"
    ],
    smjerovi: [
      { name: "Matematika", abbr: "FL" },
      { name: "Informatika", abbr: "GA" },
      { name: "Kemija", abbr: "GA" },
      { name: "Biologija", abbr: "GA" },
      { name: "Geografija", abbr: "GA" },
      { name: "Geografija, smjer Turizam i zaštita okoliša", abbr: "GA" },
      { name: "Edukacijska rehabilitacija", abbr: "GA" },
      { name: "Pedagogija", abbr: "GA" },
      { name: "Razredna nastava", abbr: "GA" },
      { name: "Predškolski odgoj", abbr: "GA" },
      { name: "Kineziologija", abbr: "GA" },
      { name: "Glazbena umjetnost", abbr: "GA" },
      { name: "Promet i logistika", abbr: "GA" },
      { name: "Matematika i informatika", abbr: "GA" },
      { name: "Matematika i fizika", abbr: "GA" },
      { name: "Biologija i kemija", abbr: "GA" },
      { name: "Glazbena umjetnost i Etnomuzikologija", abbr: "GA" },
      { name: "Georgia", abbr: "GA" },
      { name: "Georgia", abbr: "GA" },
      { name: "Georgia", abbr: "GA" },
      { name: "Georgia", abbr: "GA" },
      { name: "Georgia", abbr: "GA" },
      { name: "Georgia", abbr: "GA" },
      { name: "Georgia", abbr: "GA" },
      { name: "Georgia", abbr: "GA" },
      { name: "Georgia", abbr: "GA" },
      { name: "Georgia", abbr: "GA" }
    ]
  }),
  // watch: {
  //   steps(val) {
  //     if (this.e1 > val) {
  //       this.e1 = val;
  //     }
  //   },
  //   vertical() {
  //     this.e1 = 2;
  //     requestAnimationFrame(() => (this.e1 = 1)); // Workarounds
  //   }
  // },

  methods: {
    nextStep(n) {
      console.log(n);
      if (n === this.steps) {
        this.e1 = 1;
      } else {
        this.e1 = n + 1;
      }
    },
    back() {
      this.e1 -= 1;
    },
    sendData() {
      console.log(this.imePrezime);
      console.log(this.JMBG);
      console.log(this.mjestoPrebivališta);
      console.log(this.datumRodenja);
      // successfullySent: true;
      if (this.successfullySent) {
        this.successSnackbar = true;
      } else {
        this.errorSnackbar = true;
      }
    },
    saveDate() {
      this.$refs.menu.save(this.datumRodenja);
      this.closeDate();
    },
    closeDate() {
      this.menu = false;
    },
    customFilter(item, queryText) {
      const text = item.name.toLowerCase();
      const searchText = queryText.toLowerCase();
      return text.indexOf(searchText) > -1;
    }
    // save() {
    //   this.isEditing = !this.isEditing;
    //   this.hasSaved = true;
    // }
  }
};
</script>

<style>
.buttonText {
  padding-top: 3px;
}
.v-stepper__wrapper {
  margin-bottom: 10px;
}
</style>


