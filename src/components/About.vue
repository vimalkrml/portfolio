<template>
  <div class="grid place-items-center h-screen">
    <div class="text-center space-y-4">
      <div class="flex flex-wrap justify-center">
        <img
          class="w-28 h-28 rounded-full ring-2 ring-gray-300 dark:ring-gray-200 p-1"
          src="../assets/profile.png"
          alt="Rounded avatar"
        />
      </div>
      <div class="text-3xl">
        <h1>{{ name }}</h1>
      </div>
      <div class="text-blue-500 font-semibold text-xl">
        <h2>{{ describe }}</h2>
      </div>
      <div class="w-[50%] mx-auto text-slate-500">
        <p>{{ content }}</p>
      </div>
      <div class="flex gap-5 justify-center">
        <button
          type="button"
          class="hover:ring-2 focus:outline-none font-medium border rounded-lg text-sm text-center inline-flex items-center gap-2 dark:hover:ring-blue-500"
        >
          <router-link to="/skills" class="flex items-center gap-2 px-3 py-2">
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
        <button
          type="button"
          class="hover:ring-2 focus:outline-none font-medium border rounded-lg text-sm text-center inline-flex items-center gap-2 dark:hover:ring-blue-500"
        >
          <router-link to="/projects" class="flex items-center gap-2 px-3 py-2">
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
        <button
          type="button"
          class="hover:ring-2 focus:outline-none font-medium border rounded-lg text-sm text-center inline-flex items-center gap-2 dark:hover:ring-blue-500"
        >
          <router-link to="/contact" class="flex items-center gap-2 px-3 py-2">
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
                d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"
              /></svg
            ><span>Contact</span>
          </router-link>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import json from "../db.json";
export default {
  data() {
    return {
      name: json.about[0].name,
      describe: json.about[0].describe,
      content: json.about[0].content,
    };
  },
};
</script>

<style></style>
