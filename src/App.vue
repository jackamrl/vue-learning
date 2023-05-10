<script >
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      greet: "Salut",
      name: "Jack Dev",
      header: "Sign up for the Giveaway",
      text: "Tentez de gagnez les goodies DIDO en jouant le jeu",
    };
  },
};
</script>

<template>
  <h1>{{ greet }} {{ name }}</h1>
  <Modal :header="header" :text="text" theme="sale" />
</template>

<style >
</style>
