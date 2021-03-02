<template>
  <nav>
    <div>Logo</div>
    <CartBadge />
  </nav>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import CartBadge from '@/components/CartBadge.vue';

export default defineComponent({
  components: {
    CartBadge,
  },
});
</script>

<style></style>
