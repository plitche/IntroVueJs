<template>
  <div class="about">
    <h1>This is an about page</h1>
    <KossieCoder>
      <template #header="props">
        <p>header11 {{ props.kossie }}</p>
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
