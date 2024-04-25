<template>
  <div class="plan">
      <div class="description">
          <span class="title">
              {{ title }}
          </span>
      </div>
    </div>
</template>

<script setup>
//Macro
defineProps({
  title: {
      type: String,
      required: true
  }
});
</script>