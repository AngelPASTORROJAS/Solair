<template>
  <div class="row justify-center items-start q-py-md q-px-xl">
    <div class="column justify-evenly description">
      <h2 class="text-custom-h2 text-center">Avec Sol’Air, trouvez des voyages qui vous ressemblent.</h2>
      <p class="text-custom-p text-center">
        Sol’Air est une agence de voyage qui trouve pour vous la destination qui
        vous correspond, en France. Le concept ? Vous répondez à une série de 10
        questions, et vous n’avez plus qu’à faire vos valises et partir !
      </p>
      <p class="text-custom-p text-center">
        En bonus : retrouvez une sélection de logements, de moyens de transport et
        d’activité, ainsi que d’autres destinations similaires.
      </p>
      <a class="text-center" href="#/qui-sommes-nous">
        <button class="button-select-custom">En savoir plus</button>
      </a>
    </div>
    <img class="q-ma-xl" src="./../../assets/img/ciel.png" alt="">
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
export default defineComponent({
  name: 'AccueilDescription',
});
</script>

<style lang="scss" scoped>
h2 {
  text-transform: capitalize;
}

img {
  width: 35em;
}

.description {
  width: 30em;
}
</style>
