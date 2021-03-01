<template>
  <div class="home">
    <div v-if="error">Error :</div>
    <Suspense v-else>
      <template #default>
        <ProductsList />
      </template>
      <template #fallback>loading...</template>
    </Suspense>
  </div>
</template>

<script lang="ts">
import { defineComponent, onErrorCaptured, Ref, ref } from 'vue';
import ProductsList from '@/components/ProductsList.vue';
export default defineComponent({
  name: 'Home',
  components: {
    ProductsList,
  },
  setup() {
    const error: Ref<unknown> = ref();
    onErrorCaptured(errorCaptured => {
      error.value = errorCaptured;
    });

    return {
      error,
    };
  },
});
</script>
