<template>
  <div class="flex w-full">
      <div class="m-auto">
        <h1 class="text-center text-4xl my-2">Vue 3 Practice Homepage</h1>
        <div class="">
          <div class="flex justify-between my-3">
            <a href="https://github.com/Priyansh-09/Vue.js-Practice" target="blank">Github Source Code</a>
            <a href="https://www.youtube.com/watch?v=e-E0UB-YDRk" target="blank">Tutorial Video</a>
          </div>

          <div class="flex justify-center">
            <div class="w-11/12 grid grid-cols-2 md:grid-cols-3 gap-4">
              <div v-for="app in list" :key="app.path" class="text-left my-4 border shadow-md p-2">
                <router-link class="w-full" :to="app.path">
                  <p class="text-xl font-semibold">🔷 {{ app.title }}</p>
                </router-link>
                <div>
                  <div class="font-semibold mt-2">Topic Covered:</div>
                  <p v-for="topic in app.concepts" :key="topic">{{ topic }}</p>
                </div>
              </div>
              <div class="text-left my-4 border shadow-md p-2">
                <p class="text-xl font-semibold">🔷 Login</p>
                <div class="">
                  <div class="text-lg font-semibold">Topic Covered:</div>
                  <p v-for="topic in login.concepts" :key="topic">{{ topic }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
  </div>

</template>

<script>
import { ref } from "vue";
export default {
  setup() {
    const list = ref([
      {
        path: "/todo",
        title: "To-Do List",
        concepts: [
          "v-for, v-bind, v-model, v-on",
          "methods",
          "computed properties ( getters & setters)",
          "vue components",
        ],
      },
      {
        path: "/calendar",
        title: "Calendar",
        concepts: ["Javascript Date", "Vue Router"],
      },
      {
        path: "/markdown",
        title: "Markdown",
        concepts: ["Using External Library", "Vue Mixins"],
      },
      {
        path: "/slider",
        title: "Slider Carousel",
        concepts: [
          "Vue Transition & Animation",
          "virtual DOM",
          "lifecycle hooks",
        ],
      },
      {
        path: "/calculator",
        title: "Calculator",
        concepts: [
          "resuable composition api",
          "window event listener",
          "Composition API",
        ],
      },
      {
        path: "/reuse-modal",
        title: "Re-Useable Modal",
        concepts: ["slots", "named slots"],
      },
      {
        path: "/chat",
        title: "Real-Time Chat App",
        concepts: [
          "Firebase Realtime Database",
          "vuex v4",
          "Custom Router middleware",
        ],
      },
      {
        path: "/user-crud",
        title: "User CRUD",
        concepts: [
          "using axios",
          "external API",
          "reactive vue3 api",
          "pagination",
          "envirnment variable (.env file)",
        ],
      },
      {
        path: "/tensorflow",
        title: "Object Detection",
        concepts: [
          "Using Tensorflow with Vue",
          "Device Camera Open",
          "Working with Canvas",
        ],
      },
    ]);
    
    const login = ref({
      title: "Login Modal",
      concepts: [
        "Create Modal",
        "Vue Custom Events Emitting",
        "Form Handling",
        "firebase authentication",
        "loading effect",
        "Template Refs",
        "component props",
        "firebase google login",
        "Refactoring with component",
        " vue3 teleport",
      ],
    });

    return { list, login };
  },
}
</script>
