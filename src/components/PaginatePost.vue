<script setup>
defineProps(["inicio", "fin", "totalPosts"]);
const emit = defineEmits(["next", "prev"]);

const activarSiguiente = () => {
  console.log("me diste a siguiente");
  emit("next");
};
</script>

<template>
  <div class="btn-group" role="group" aria-label="Basic example">
    <button
      :disabled="inicio <= 0"
      @click="emit('prev')"
      type="button"
      class="btn btn-outline-primary"
    >
      Previous {{ inicio }}
    </button>
    <button
      :disabled="fin >= totalPosts"
      @click="activarSiguiente"
      type="button"
      class="btn btn-outline-primary"
    >
      Next {{ fin }}
    </button>
  </div>
</template>
