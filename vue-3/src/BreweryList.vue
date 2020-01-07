<template>
  <h1>Brewery List</h1>
  City:
  <select v-model="searchCity">
    <option value="">Select City</option>
    <option value="cleveland">Cleveland</option>
    <option value="columbus">Columbus</option>
    <option value="cincinnati">Cincinnati</option>
    <option value="pittsburgh">Pittsburgh</option>
    <option value="detroit">Detroit</option>
    <option value="philadelphia">Philadelphia</option>
  </select>
  Order By:
  <select v-model="orderBy">
    <option value="id">Id</option>
    <option value="name">Name</option>
  </select>
  <ul>
    <li v-for="brewery in breweriesSorted" :key="brewery.id">
      {{ brewery.name }}
    </li>
  </ul>
</template>

<script>
import { ref, computed, watch, reactive } from 'vue';
import * as _ from 'lodash';

const API_URL = 'https://api.openbrewerydb.org/breweries';

export default {
  setup() {
    const orderBy = ref('name');
    const breweriesSorted = computed(() =>
      _.sortBy(breweries.value, orderBy.value)
    );

    const searchCity = ref('');
    let breweries = ref([]);

    watch(() => {
      if (searchCity.value != '') {
        fetch(`${API_URL}?by_city=${searchCity.value}`)
          .then(response => {
            return response.json();
          })
          .then(data => {
            breweries.value = data;
          });
      }
    });

    return { breweriesSorted, searchCity, orderBy };
  }
};
</script>

<style></style>
