<template>
  <div class="about">
    <h1>This is an about page</h1>
    <KossieCoder>
      <template #header="{ kossie }">
        <p>header11 {{ kossie }}</p>
      </template>
      <template v-slot:default>
        hello
      </template>
    </KossieCoder>
  </div>
</template>

<script>
import KossieCoder from '@/components/KossieCoder.vue'

export default {
  components: {
    KossieCoder
  }
}
</script>
