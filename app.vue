<template>
  <NuxtLoadingIndicator color="#B5E853" />
  <div class="flex flex-col min-h-screen">
    <AppNavbar />
    <div class="h-32"></div>
    <UContainer>
      <NuxtPage />
    </UContainer>
    <div class="h-32"></div>
    <AppFooter />
</div>
</template>

<style>
.page-enter-active,
.page-leave-active {
  transition: all 0.2s;
}

.page-leave-to {
  opacity: 0;
  transform: translateY(-5px);
}

.page-enter-from {
  opacity: 0;
  transform: translateY(5px);
}
</style>
