<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <!-- <Modal heading="Sign up for the Givaway!" text="Grab your ninja swag for half price!" /> -->
  <teleport to="#modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <!-- Named Slot = links -->
        <a href="#">Sign Up</a>
        <a href="#">More Info</a>
      </template>
      <h1>Ninja Giveaway!</h1>
      <p>Grab your ninja swag</p>
    </Modal>
  </teleport>

  <teleport to="#modals" v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <h1>Sign up to the Newsletter</h1>
      <p>For updates and promo codes!</p>
    </Modal>
  </teleport>

  <button @click="toggleModal">Open Modal</button>
  <button @click="toggleModalTwo">open modal 2</button>
</template>

<script>
import Modal from './components/Modal';
export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My First Vue App!',
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
