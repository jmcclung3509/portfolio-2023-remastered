<template>
	<section class="section info  py-36 space-y-4">

		<SkillMain />

	</section>
	<section class="section animate bg-default-dark  relative contact space-y-7 mt-[-60px]">
		<div class="mx-auto contact-container w-full absolute top-[-50px] left-0 right-0">
			<Nuxt-link to="/contact"
				class=" contact h-[100px] w-1/5 min-w-fit p-4 z-100 mx-auto rounded-2xl flex flex-col items-center justify-center space-y-4 button">

				<p class="inner-button text-light-peach text-1.5xl">
					Let's connect!</p>
			</Nuxt-link>
		</div>

		<div class="pt-[50px]">
			<div class="flex flex-col space-y-4 items-center">
				<Yoda />

				<h4 class="quote w-full md:w-2/3 lg:w-1/2 mx-auto text-extra-light-purple text-center text-light">
					Pass on what you have learned. Strength, mastery,
					hmmm... but weakness, folly, failure, also. Yes,
					failure, most of all. The greatest teacher, failure is.
				</h4>
				<p class="cite text-extra-light-purple caps font-light">&mdash; Yoda</p>
			</div>
		</div>


		<div class="social-icons flex flex-row justify-center gap-7">
			<a href="https://github.com/jmcclung3509" target="_blank">
				<font-awesome-icon class="social-icon text-1.5xl text-extra-light-purple hover:text-orange"
					:icon="['fab', 'github']" /></a>
			<a href="https://www.linkedin.com/in/jessica-turner-94b549229/" target="_blank">
				<font-awesome-icon class="social-icon text-1.5xl text-extra-light-purple hover:text-orange"
					:icon="['fab', 'linkedin']" />
			</a>
		</div>
		<div class="flex justify-center pt-4">
			<p class="text-[12px] caps text-default-dark font-light text-center">
				Designed & developed by me using Adobe Illustrator,
				Figma, Vue, Nuxt and Tailwind 💜 2023
			</p>
		</div>

	</section>
</template>

<script setup>
const route = useRoute();
const size = useScreenSize().size;
const { isMobile } = useScreenSize();
</script>

<style lang="scss">
@import "@/assets/scss/variables.scss";

header.main {
	background: $light-peach;
}
</style>