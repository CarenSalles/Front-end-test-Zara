<script setup>
import usePodcastService from '../services/PodcastService.js';
import { ref, onMounted } from 'vue';
import CardComponent from '../components/CardComponent.vue';

const { getPodcasts} = usePodcastService(); // acá hace una const para llamar la funcion del servicio da peticion de la API. 

const podcasts = ref([]); // constante para receber los datos de la api en un array.

onMounted(async () => {                    // no momento de montar faz uma chamada assíncrona
    podcasts.value = await getPodcasts();
});
</script>
<template>
    <CardComponent/>
    <div v-if="podcasts.length">
      <h2>Top 100 podcasts en Tecnología</h2>
        <ul>
          <li v-for= "(podcast, index) in podcasts" :key="podcast ['im:name'].label">
            {{ index + 1 }} {{ podcast['im:name'].label }}
            {{ index + 1 }} {{ podcast['im:artist'].label }}
            <img :src="podcast['im:image'][1]['label']" alt="Podcast Image">
          </li>
        </ul>
    </div>
    <div v-else>
        <p>Cargando podcasts...</p>
    </div>
</template>

<style lang="scss" scoped >

</style>
