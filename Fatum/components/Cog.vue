<template>
  <div>
    <img src="/Cog.svg" alt="Cog" class="w-8 h-8 cog-effects opacity-5" />
  </div>
</template>

<style scoped>
.cog-effects {
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  cursor: pointer;
}

.cog-effects:hover {
  transform: scale(1.15);
  opacity: 100%;
}

</style>