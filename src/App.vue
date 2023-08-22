<script setup>
import HelloWorld from "./components/HelloWorld.vue";
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <button id="modalBtn" class="modalBtn" @click="showModal = true">Click!</button>
  </main>
  <div v-if="showModal" class="modal">
    <div class="modal-content" style="width: 1200px; height: 500px">
      <span class="close" @click="showModal = false">&times;</span>
      <p>모달 내용을 입력하세요.</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showModal: false,
    };
  },
  mounted() {
    console.log("test");
  },
  methods: {
    async handleClick() {
      this.isModalViewed = true;
    },
  },
};
</script>

<style scoped>
.modal {
  display: block;
  position: fixed;
  z-index: 1;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.4);
}

.modal-content {
  background-color: white;
  margin: 15% auto;
  padding: 20px;
  border: 1px solid #888;
  width: 50%;
}

.close {
  color: #aaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
  cursor: pointer;
}
.modalBtn {
  width: 100px;
  height: 50px;
  background-color: lightblue;
  font-weight: bold;
}
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
