<template>
  <div class="relative h-full min-h-screen bg-dark">
    <!--navbar + logo-->
    <TheHeader/>

    <!--body-->
    <div class="py-20 px-5 flex flex-row justify-center w-screen">
      <router-view/>
    </div>

    <!--padder-->
    <div class="p-10"></div>

    <!--cat + footer-->
    <TheCat/>
    <TheFooter/>
  </div>
</template>

<script lang="ts">
import {defineComponent, onMounted, onUnmounted, ref} from 'vue';
import TheHeader from '@/components/TheHeader.vue';
import TheFooter from '@/components/TheFooter.vue';
import TheCat from '@/components/TheCat.vue';

export default defineComponent({
  components: {TheCat, TheFooter, TheHeader},
  setup() {
    const windowWidth = ref(window.innerWidth);
    const onWidthChange = () => {
      windowWidth.value = window.innerWidth;
    };
    onMounted(() => window.addEventListener('resize', onWidthChange));
    onUnmounted(() => window.removeEventListener('resize', onWidthChange));

    return {
      windowWidth,
    };
  },
});
</script>

<style>
* {
  @apply text-center text-white;
  font-family: 'Press Start 2P', monospace;
}

a {
  @apply text-rb-blue !important;
}

a:hover {
  @apply text-rb-pink !important;
}

.bg-dark {
  background-color: #21252A;
}
</style>
