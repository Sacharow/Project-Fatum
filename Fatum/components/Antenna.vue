<template>
  <div class="antenna-wrapper">
    <img src="/Antenna.svg" alt="Antenna" class="w-64 h-64 antenna-effects" />
  </div>
</template>

<style scoped>
.antenna-effects {
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  cursor: pointer;
}

.antenna-effects:hover {
  transform: scale(1.15);
}

.antenna-wrapper:hover {
  animation: pulse 5s infinite;
}

@keyframes pulse {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.05); }
}
</style>