<template>
  <v-container class="fill-height">
    <v-responsive class=" fill-height">


      <v-row class="d-flex justify-center mt-10">


        <v-col>
          <v-select label="Select Year" :items="yearList" v-model="selectedYear"></v-select>
        </v-col>
        <v-col>
          <v-select label="Disease Condition" :items="diseaseCodes" item-title="name" item-value="code"
            v-model="selectedDisease"></v-select>
        </v-col>
        <v-col cols="auto">
          <v-btn :disabled="!isDisabled" @click="submit" :loading="isLoading" ripple color="#5865f2" class="d-inline"
            size="x-large">
            Submit
          </v-btn>
        </v-col>





      </v-row>

      <v-snackbar color="red" v-model="snackbar" timeout="2000">
        Internal error... please try again later

      </v-snackbar>


      <v-row>
        <v-col class="mt-15 d-flex justify-center align-center">
          <div class="output">
            <h3 class="mb-2">OUTCOME </h3>
            <div>
              {{ outcome }}
            </div>
          </div>
        </v-col>
      </v-row>

    </v-responsive>
  </v-container>
</template>

<script setup>
import { ref, computed } from 'vue'
import axios from 'axios'

const yearList = [
  2023, 2022, 2021, 2020, 2019, 2018, 2017, 2016, 2015, 2014,
  2013, 2012, 2011, 2010, 2009, 2008, 2007, 2006, 2005, 2004,
  2003, 2002, 2001, 2000, 1999, 1998, 1997, 1996, 1995, 1994,
  1993, 1992, 1991, 1990
]
const snackbar = ref(false)


const diseaseCodes = [
  {
    code: 10509002,
    name: "Acute bronchitis (disorder)"
  },
  {
    code: 65363002,
    name: "Otitis media"
  },
  {
    code: 43878008,
    name: "Streptococcal sore throat (disorder)"
  },
  {
    code: 65966004,
    name: "Fracture of forearm"
  },
  {
    code: 232353008,
    name: "Perennial allergic rhinitis with seasonal variation"
  },
  {
    code: 446096008,
    name: "Perennial allergic rhinitis"
  },
  {
    code: 284551006,
    name: "Laceration of foot"
  },
  {
    code: 44465007,
    name: "Sprain of ankle"
  },
]


const selectedDisease = ref('')
const selectedYear = ref('')
const isLoading = ref(false)
const outcome = ref('--')

const isDisabled = computed(() => {
  return selectedDisease.value !== '' && selectedYear.value !== '';
});

const submit = async () => {

  isLoading.value = true
  outcome.value = '--'
  try {
    const res = await axios.get(`https://gosh-synth-fhir.azurehealthcareapis.com/Condition?onset-date=${selectedYear.value}&code=${selectedDisease.value}&_summary=count`, {
      headers: {
        'Authorization': `Bearer ${import.meta.env.VITE_TOKEN}`,
        'Content-Type': 'application/fhir+json'
      }
    })

    isLoading.value = false
    outcome.value = res.data.total
    console.log(res);

  } catch (error) {
    isLoading.value = false
    snackbar.value = true
    outcome.value = '--'

    console.log(error);
  }
}



</script>


<style lang="scss">
.output {

  h3 {
    text-align: center;
    letter-spacing: 0.167rem;
  }

  div {
    padding: 0.25em 1.5em;
    aspect-ratio: 1;
    background-color: #f6f6f6;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 2.5rem;
    font-weight: bold;
    color: #5865f2;
    border: 1px dashed #ddd;
  }


}
</style>