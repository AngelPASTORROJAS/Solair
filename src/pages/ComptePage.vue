<template>
  <HeaderCustom label="Mon Compte" />
  <FooterComponent />
</template>
<script lang="ts">
import { defineComponent } from 'vue';
import HeaderCustom from 'src/components/HeaderCustom.vue';
import FooterComponent from 'src/components/FooterComponent.vue';

export default defineComponent({
  name: 'ComptePage',
  components: {
    HeaderCustom,
    FooterComponent,
  },
});
</script>
<style lang="scss" scoped></style>
