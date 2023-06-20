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
      showModal: false
    };
  },
  methods: {
    toogleModal() {
      this.showModal = !this.showModal
    }
  }

};
</script>

<template>
  <h1>{{ greet }} {{ name }}</h1>
  <div v-if="showModal">
    <Modal  theme="sale" @close="toogleModal" >
      <template v-slot:links>
        <a href="#">Sign up</a>
        <a href="#">Sign in</a>
      </template>
        <h1>{{ header }}</h1>
        <p>{{ text }}</p>

      </Modal>
  </div>
  <button @click="toogleModal">Open modal</button>
</template>

<style >
h1 {
  font-size: 2rem;
  font-weight: 700;
  text-align: center;

}
</style>
