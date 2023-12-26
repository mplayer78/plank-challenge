<script setup lang="ts">
  import Timer from './components/Timer.vue'
  const currentYear = new Date().getFullYear()
  const startOfYear = Number(new Date(`01/01/${currentYear}`))
  const now = Number(new Date())
  const elapsed = now - startOfYear
  const elapsedDays = Math.floor(elapsed / 1000 / 60 / 60 / 24)
  
  const secondsToMinutes = (seconds: number): string => {
    return `${Math.floor(seconds / 60)}:${seconds % 60}`
  }
</script>

<template>
  <header>
    <h1>Welcome to the Plank Challenge {{ currentYear }}</h1>
  </header>

  <main>
    <div>
      <h3>
        Today's challenge is
      </h3>
    </div>
    <div>
      <h1>
        {{ secondsToMinutes(elapsedDays) }}
      </h1>
    </div>
    <div>
      <h3>
        seconds
      </h3>
    </div>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
