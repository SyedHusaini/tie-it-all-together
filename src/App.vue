<template>
  <div class="subpixel-antialiased">
    <Navbar />
    <div class="transition-colors duration-500">
      <router-view v-slot="{ Component }">
        <transition name="router-anim">
          <!-- <keep-alive include="ViewStats"> -->
          <component :is="Component" />
          <!-- </keep-alive> -->
        </transition>
      </router-view>
    </div>
  </div>
</template>

<script>
import Navbar from "./components/Navbar";
export default {
  components: { Navbar },
};
</script>

<style>
a:focus {
  outline: none;
}

.body-height {
  height: 90%;
}

.router-anim-enter-active {
  animation: coming 0.4s;
  animation-delay: 0.4s;
  opacity: 0;
}
.router-anim-leave-active {
  animation: going 0.4s;
}
@keyframes going {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@keyframes coming {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>
