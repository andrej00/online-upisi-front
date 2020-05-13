<template>
  <div class="container">
            <b-container>
                <b-row>
                    <b-col sm="12" md="4">
                        <div class="info-container">
                        <h2>Odaberi znanje</h2>
                        <div class="info-logo-section">
                            <img src="../assets/logofpmoz.png" height="100px" width="220px">
                        </div>
                        <div class="info-icons">
                            <b-list-group>
                                <b-list-group-item>
                                        <i class="material-icons">phone_in_talk</i>
                                        +387 (0)36 355-455
                                </b-list-group-item>
                                <b-list-group-item>
                                        <i class="material-icons">location_on</i>
                                        Matice Hrvatske b.b.
                                        88000 Mostar
                                </b-list-group-item>
                                <b-list-group-item>
                                        <i class="material-icons">email</i>
                                        fpmoz@sum.ba
                                </b-list-group-item>
                            </b-list-group>
                        </div>
                        </div>
                    </b-col>
                    <b-col sm="12" md="8">
                        <div class="info-header">
                            <h1>Troškovi plaćanja</h1>
                        </div>
                        <div>
                            <b-table striped hover :items="items"></b-table>
                        </div>
                    </b-col>
                </b-row>
            </b-container>
    </div>
</template>

<script>
  export default {
    name: 'Info',
    data() {
      return {
        items: [
          { preddiplomski_studij: 'Fakultet prirodoslovno-matematičkih i odgojnih znanosti', a: 200, b: 750, c: 750, _rowVariant: 'secondary'},
          { preddiplomski_studij: 'Stručni studij kineziologije', a: '', b: '', c: 1000},
          { preddiplomski_studij: 'Studij glazbene umjetnosti', a: 200, b: 750, c: '', _rowVariant: 'secondary'},
          { preddiplomski_studij: 'Instrumentalni smjer na studiju glazbene umjetnosti', a: 350, b: 1000, c: ''},
          { preddiplomski_studij: 'Edukacijska rehabilitacija', a: '', b: 1000, c: 1000, _rowVariant: 'secondary'},
          { preddiplomski_studij: 'Sveučilišni odjel Promet i logistika, smjer Cestovni promet', a: '', b: 1000, c: 1000},
          { preddiplomski_studij: 'Dislocirana nastava - Orašje', a: '', b: 900, c: 900, _rowVariant: 'secondary'},
          { preddiplomski_studij: 'Dislocirana nastava - Kreševo', a: '', b: 1000, c: ''},
        ]
      }
    }
  }
</script>

<style>
    .info-header, .info-container{
        text-align: center;
    }

    .info-container h2{
        color: #1a4283;
    }

    .info-logo-section{
        margin-top: 1.8em;
    }

    .info-icons{
        margin-top: 1em;
        text-align: left;
    }

    .info-icons i{
        margin-right: 0.5em;
    }
</style>