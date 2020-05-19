<template>
  <v-app :style="{background: $vuetify.theme.themes.light.background}">
    <v-container>
      <v-layout row class="ma-4">
        <v-app style="background-color: grey lighten-1;" class="rounded">
          <v-row>
            <v-col cols="12" md="8" class="ligne">
              <v-container>
                <v-row>
                  <v-col cols="12" md="9" offset-md="1">
                    <v-text-field label="Search" prepared-inner-icon="search"></v-text-field>
                  </v-col>
                  <v-col cols="12" md="2" align="center" justify="center">
                   <v-badge color="error" overlap class="mt-5">
                     <template slot="badge">2</template>
                     <v-icon color="tertiary">mdi-bell</v-icon>
                   </v-badge>
                  </v-col>
                  <v-col cols="12" md="12">
                    <h1 class="headline mb-2 grey--text"> Money Status</h1>
                    <template>
                      <div id="app">
                        <GChart
                        type="ColumnChart"
                        :data ="chartData"
                        :options= "chartOptions"/>

                      </div>
                    </template>
                  </v-col>
                  
                </v-row>
              </v-container>
            </v-col>
          </v-row>
        </v-app>
      </v-layout>
    </v-container>
  </v-app>
</template>

<script>



export default {
  data:()=>({
    chartData:[
      ["Year", "Sales", "Expenses", "Profit"],
      ["2015", "1000", "400", "200"],
      ["2016", "1500", "300", "400"],
      ["2017", "800", "350", "200"],
      ["2018", "2200", "300", "500"],
      ["2019", "1800", "700", "300"],
      ["2020", "400", "300", "-100"],
    ],
    chartOptions:{
      chart:{
        title: "Company Performance",
        subtitiles: "Sales, Expenses, and Profit: 2015-2020"
      }
    }

  }),
  name: 'Home',
  components: {

  },

  computed:{
    theme(){
        return(this.$vuetify.theme.dark) ? 'dark' : 'light'
    }
  }
}
</script>

<style scoped>
.rounded{
  border-radius: 30px;
}
.light{
  border-right: solid 1px #95a5a6;
}
</style>