<script>
import HelloWorld from './components/HelloWorld.vue';
export default defineComponent({
  name: 'test',
  components: {},
  setup() {
    const profileTopImg = getImageUrl('it-products');

    function getImageUrl(name) {
      return new URL(`/src/assets/images/avatars/${name}.jpg`, import.meta.url)
        .href;
    }

    return {
      profileTopImg,
    };
  },
});
</script>

<template>
  <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img
        :src="profileTopImg"
        alt="My picture"
        class="h-50px w-60px rounded"
      />
    </a>
  </div>
  <HelloWorld msg="Vite + Vue" />
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
