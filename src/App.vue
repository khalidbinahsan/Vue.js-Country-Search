<script setup>
import { ref, reactive } from 'vue';
import { countries } from './data/countries';
const search = ref('');
function filteredCountry(){
  return countries.filter(country => {
    return country.name.toLocaleLowerCase().startsWith(search.value.toLocaleLowerCase());
  })
}
</script>

<template>
<section class="container mx-auto max-w-[800px] py-20 px-4">
<h2 class="text-4xl">Search your country</h2>
<input v-model="search" type="search" placeholder="Type here" class="input border input-bordered input-info w-full max-w-xs p-2 my-3" />
<ul>
  <li v-for="(country, index) in filteredCountry()" :key="index">{{ country.name }}<span> ({{ country.code }})</span></li>
</ul>
</section>
</template>

<style scoped>

</style>
