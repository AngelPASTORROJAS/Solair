<template>
  <HeaderCustom :label="destination.nom ?? ''" />
  <div class="row justify-center items-start q-py-md q-px-xl q-gutter-lg">
    <div class="column justify-evenly article">
      <h2 class="text-custom-h2 text-center">{{ destination.titre }}</h2>
      <p class="text-custom-p text-center">{{ destination.article }}</p>
    </div>
    <img class="q-ma-xl" :src="destination.url_image" :alt="destination.description"/>
  </div>
  <FooterComponent />
</template>
<script lang="ts">
import { defineComponent, onMounted, ref } from 'vue';
import HeaderCustom from 'src/components/HeaderCustom.vue';
import FooterComponent from 'src/components/FooterComponent.vue';
import { useQuasar } from 'quasar';
import { Destination } from 'src/api/back_solair/models/Destination';
import { solairAPI } from 'src/api/back_solair';
import { useRouter } from 'vue-router';

export default defineComponent({
  name: 'DestinationPage',
  setup() {
    const $q = useQuasar();
    const destination = ref({} as Destination);
      const router = useRouter();
    onMounted(async () => {
      try {
        $q.loading.show();
        destination.value = await solairAPI.destination.getDestinationsRandomAsync();
      // eslint-disable-next-line @typescript-eslint/no-explicit-any
      } catch (error:any) {
        if(error.response && error.response.status === 401){
          router.push({name:'ErrorUnautorized'})
        }
        console.error(error);

      } finally {
        $q.loading.hide();
      }
    });
    return {
      destination,
    };
  },
  components: {
    HeaderCustom,
    FooterComponent,
  },
});
</script>
<style lang="scss" scoped>
img {
  width: 38em;
  border-radius: 20px;
}

.article {
  width: 30em;
}

.row {
  display: flex;
  flex-wrap: wrap;
}
</style>
