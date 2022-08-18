<template>
  <div class="p-6">
    <div class="px-10 flex items-center gap-3">
      <button
        class="hover:ring-2 px-1 font-medium rounded-lg text-sm text-center flex items-center dark:hover:ring-blue-500"
      >
        <router-link class="px-1 py-1.5 flex items-center gap-2" to="/about">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-4 w-4"
            fill="none"
            viewBox="0 2 24 24"
            stroke="currentColor"
            stroke-width="2"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6"
            /></svg
          ><span>Home</span>
        </router-link>
      </button>
      <button
        class="hover:ring-2 px-1 font-medium rounded-lg text-sm text-center flex items-center dark:hover:ring-blue-500"
      >
        <router-link class="px-1 py-1.5 flex items-center gap-2" to="/projects">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-4 w-4"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
            stroke-width="2"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M3 7v10a2 2 0 002 2h14a2 2 0 002-2V9a2 2 0 00-2-2h-6l-2-2H5a2 2 0 00-2 2z"
            /></svg
          ><span>Projects</span>
        </router-link>
      </button>
    </div>
    <div class="m-10 grid place-items-center h-screen">
      <h1 class="mb-10 text-2xl">Skills</h1>
      <div
        class="max-w-5xl bg-white mb-5 space-y-3 border-b border-blue-200 pb-2"
        v-for="skill in skills"
        :key="skill.id"
      >
        <h5
          class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-blue-500"
        >
          {{ skill.title }}
        </h5>

        <p class="mb-3 font-normal text-gray-700 dark:text-gray-500">
          {{ skill.about }}
        </p>

        <p>Proficiency Level - {{ skill.level }}</p>
        <a
          :href="skill.learnmore"
          class="inline-flex items-center text-sm font-medium text-center hover:text-blue-500"
        >
          Learn more
          <svg
            aria-hidden="true"
            class="ml-2 -mr-1 w-4 h-4"
            fill="currentColor"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              fill-rule="evenodd"
              d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z"
              clip-rule="evenodd"
            ></path>
          </svg>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      skills: "",
    };
  },
  async mounted() {
    await fetch("src/db.json")
      .then((res) => res.json())
      .then((data) => {
        this.skills = data.skills;
      });
  },
};
</script>

<style></style>
