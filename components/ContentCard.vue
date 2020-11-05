<template>
  <div class="card">
    <div class="card-content">
      <div class="content">
        <slot />
      </div>
    </div>
  </div>
</template>

<style scoped>
.card {
  background: #ffffff;
  max-width: 800px;
  border: 1px solid #0f2540;
  box-shadow: 3px 3px 0 0 #0f2540;
}
.card-content {
  padding: 20px;
}
</style>
