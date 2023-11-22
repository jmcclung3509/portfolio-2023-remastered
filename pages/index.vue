<template>
    <main class="relative section dark">
        <section class="section fold hero flex justify-center items-center relative dark">
            <div
                class="flex flex-col space-y-4 lg:space-y-7 container mx-auto text-container items-start justify-center  p-7 ">

                <h1
                    class="text-3xl md:text-5xl lg:text-7xl 3xl:text-[8rem] text-default-dark md:w-[300%] text-center md:text-left">
                    <span v-for="(letter, index) in formattedHeroText" class="letter" :key="index"
                        :style="{ 'animation-delay': index * 0.1 + 's' }">{{ letter }}
                    </span>
                </h1>
                <h2
                    class="text-1xl md:text-1.5xl 3xl:text-2xl text-purple-dark font-normal appear text-center md:text-left md:w-[200%]">
                    I design and build things for the web.
                </h2>

            </div>

            <div class="flex justify-center pt-14 fixed bottom-5">
                <p class="text-[12px] caps text-light-peach font-light text-center">
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

</script>

<style lang="scss">
.letter {
    animation-name: slideDownAnimation;
    animation-duration: 0.8s;
    animation-fill-mode: both;
    opacity: 0;
}
</style>