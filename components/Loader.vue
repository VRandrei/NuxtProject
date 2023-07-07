<template>
  <div v-if="shouldShowLoader" class="loader">
    <div class="wave "></div>
    <div class="wave"></div>
  </div>
</template>

<script>
export default {
  computed: {
    shouldShowLoader() {
      if (process.client) {
        return window.innerWidth > 950;
      }
      return true;
    },
  },
};
</script>

<style scoped>
.loader {
  width: 200px;
  height: 200px;
  border-radius: 50%;
  position: relative;
  box-shadow: 0 0 30px 4px rgba(0, 0, 0, 0.5) inset, 0 5px 12px rgba(0, 0, 0, 0.15);
  overflow: hidden;
}

.wave {
  position: absolute;
  width: 100%;
  height: 100%;
  border-radius: 45%;
  top: -40%;
  background-color: rgb(17 24 39 / 1);
  animation: wave 5s linear infinite;
}

.wave:nth-child(2) {
  border-radius: 30%;
  background: rgba(122, 122, 122, 0.4);
  animation: wave 5s linear infinite;
}

@keyframes wave {
  0% {
    transform: rotate(0);
  }

  100% {
    transform: rotate(360deg);
  }
}

@media (max-width: 950px) {
  .loader {
    display: none;
  }
}
</style>