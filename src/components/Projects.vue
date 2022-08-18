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
        <router-link class="px-1 py-1.5 flex items-center gap-2" to="/skills">
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
              d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.747 0 3.332.477 4.5 1.253v13C19.832 18.477 18.247 18 16.5 18c-1.746 0-3.332.477-4.5 1.253"
            /></svg
          ><span>Skills</span>
        </router-link>
      </button>
    </div>
    <div class="m-10 grid place-items-center h-screen">
      <h1 class="mb-10 text-2xl">Projects</h1>
      <div class="">
        <div
          class="lg:grid lg:grid-cols-3 lg:gap-6 lg:space-y-5 border-b border-gray-300 py-5"
          style="cursor: auto"
          v-for="project in projects"
          :key="project.id"
        >
          <div class="w-full h-full py-5">
            <img
              class="object-cover shadow-lg rounded-lg"
              :src="project.image"
              alt="Featured Photo"
              style="cursor: auto"
            />
          </div>

          <div class="sm:col-span-2 space-y-5" style="cursor: auto">
            <div class="flex items-center space-x-3" style="cursor: auto">
              <div class="flex items-center space-x-2" style="cursor: auto">
                <span
                  class="inline-flex items-center leading-none px-2.5 py-1.5 text-sm lg:text-sm font-medium rounded-full border border-gray-300"
                  style="cursor: auto"
                >
                  <svg
                    class="mr-1.5 h-2 w-2 brand-react"
                    fill="currentColor"
                    viewBox="0 0 8 8"
                  >
                    <circle cx="4" cy="4" r="3"></circle>
                  </svg>
                  {{ project.tag1 }}
                </span>

                <span
                  class="inline-flex items-center leading-none px-2.5 py-1.5 text-xs lg:text-sm font-medium rounded-full border border-gray-300"
                  style="cursor: auto"
                >
                  <svg
                    class="mr-1.5 h-2 w-2 brand-packages"
                    fill="currentColor"
                    viewBox="0 0 8 8"
                  >
                    <circle cx="4" cy="4" r="3"></circle>
                  </svg>
                  {{ project.tag2 }}
                </span>

                <span
                  class="inline-flex items-center leading-none px-2.5 py-1.5 text-sm lg:text-sm font-medium rounded-full border border-gray-300"
                  style="cursor: auto"
                >
                  <svg
                    class="mr-1.5 h-2 w-2 brand-tutoriel"
                    fill="currentColor"
                    viewBox="0 0 8 8"
                  >
                    <circle cx="4" cy="4" r="3"></circle>
                  </svg>
                  {{ project.tag3 }}
                </span>
              </div>
            </div>

            <div class="space-y-5" style="cursor: auto">
              <div class="flex gap-5 items-center justify-between">
                <h4
                  class="leading-6 mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-blue-500"
                  style="cursor: auto"
                >
                  {{ project.title }}
                </h4>
                <a
                  :href="project.git"
                  class="inline-flex items-end text-sm text-center hover:text-blue-500 ring-2 px-2 py-1 dark:hover:ring-blue-500 font-medium rounded-lg"
                >
                  GitHub
                </a>
              </div>

              <p
                class="mt-1 text-sm lg:text-base text-gray-500 font-normal leading-5"
                style="cursor: auto"
              >
                {{ project.content }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: "",
    };
  },
  async mounted() {
    await fetch("src/db.json")
      .then((res) => res.json())
      .then((data) => {
        this.projects = data.projects;
      });
  },
};
</script>

<style></style>
