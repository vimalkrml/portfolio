<template>
  <div class="grid place-items-center h-screen w-full relative">
    <div class="intro text-3xl uppercase cursor-pointer">
      <h1>{{ intro }}</h1>
    </div>
    <button class="absolute top-[55%]" :class="buttonStyle">
      <router-link to="/about">{{ fool }}</router-link>
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      intro: "Hi There",
      fool: "",
      buttonStyle: "",
    };
  },
  mounted() {
    setTimeout(() => {
      this.intro = "Want to know about me?";
    }, 2000);
    setTimeout(() => {
      this.fool = "Take me";
      this.buttonStyle = "activebutton";
    }, 3500);
  },
};
</script>

<style>
.intro {
  display: inline-block;
  overflow: hidden;
  white-space: nowrap;
  animation: showup 5s;
}
@keyframes showup {
  0% {
    opacity: 0;
  }
  20% {
    opacity: 1;
  }
  50% {
    opacity: 1;
  }
  80% {
    opacity: 1;
    letter-spacing: 5px;
  }
  100% {
    opacity: 1;
  }
}
.activebutton {
  color: #2563eb;
  letter-spacing: 1px;
  padding: 2px 8px;
  transition: all 3s ease;
}
</style>
