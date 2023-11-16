<template>
    <main class="relative light-section">
        <section
            class="section fold hero light flex justify-center items-center relative">
            <div
                class="flex flex-col space-y-7 lg:space-y-14 container mx-auto text-container items-start justify-center  p-7 px-28">

<h1 class="text-on-path text-1.5xl lg:text-3xl 3xl:text-3xl">
                <span
                        v-for="(letter, index) in formattedHeroText"
                        class="letter"
                        :key="index"
                        :style="{ 'animation-delay': index * 0.1 + 's' }"
                        >{{ letter }}
                    </span>
                </h1>
                <h2
                    class="text-1xl lg:text-1.5xl 3xl:text-2xl text-purple-dark appear">
                    I design and build things for the web.
                </h2>
                <div class="link-container animate-underline orange slide-in">
                    <a
                        href="#"
                        class="text-dark-purple animate-arrow orange w-fit"
                        data-go-to="projects"
                        >Skip to projects</a
                    >
                </div>
            </div>

            <div class="flex justify-center pt-14 fixed bottom-5">
                    <p class="text-[12px] caps text-light-purple font-light">
                        Designed & developed by me using Adobe Illustrator,
                        Figma, Vue, Nuxt and Tailwind 💜 2023
                    </p>
                </div>
        </section>


    </main>
</template>

<script setup>
const config = useRuntimeConfig();
const route = useRoute();
const size = useScreenSize().size;
const { isMobile } = useScreenSize();
const host = config.BASE_API_BROWSER_URL;
const title = "Jessica Turner | 2023";
const desc = " Personal website of Jessica Turner";

const image = host + "/static/images/featured-image.png";
const url = host + route.fullPath;

useHead({
    titleTemplate: title,
    meta: [
        { name: "title", content: "title" },
        { name: "description", content: "desc" },
        { hid: "og:type", property: "og:type", content: "website" },
        { hid: "og:title", property: "og:title", content: title },
        { hid: "og:url", property: "og:url", content: url },
        { hid: "og:description", property: "og:description", content: desc },
        { hid: "og:image", property: "og:image", content: image },
    ],
});

import "@/assets/css/tailwind.css";

const { bubbleLifeTime } = useBubbles();

const data = reactive({
    mobileMenuOpen: false,
});

const formattedHeroText = computed(() => {
    return "Hi, I'm Jessica.".split("");
});
const insitesButtons = [
    {
        link: "https://insites.sitezeus.com",
        label: "Live",
    },
    {
        link: "/projects/insites",
        label: "Learn more",
    },
];
const nicksButtons = [
    {
        link: "https://deft-gingersnap-b9df5d.netlify.app/",
        label: "Live",
    },
    {
        link: "https://github.com/jmcclung3509/nuxt-nicks-restaurant",
        label: "Repo",
    },
    {
        link: "/projects/nicks",
        label: "Learn more",
    },
];
const stickyButtons = [
    {
        link: "https://super-sticky-notes.vercel.app/",
        label: "Live",
    },
    {
        link: "https://github.com/jmcclung3509/super-sticky-notes",
        label: "Repo",
    },
    {
        link: "/projects/sticky",
        label: "Learn more",
    },
];
const quizzicalButtons = [
    {
        link: "https://my-quizzical-app.vercel.app/",
        label: "Live",
    },
    {
        link: "https://github.com/jmcclung3509/quizzical_react_project_scrimba",
        label: "Repo",
    },
    {
        link: "/projects/quizzical",
        label: "Learn more",
    },
];
</script>

<style lang="scss">
.letter {
    animation-name: slideDownAnimation;
    animation-duration: 0.8s;
    animation-fill-mode: both;
    opacity: 0;
}
</style>