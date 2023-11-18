<template>
	<header
		class="main flex w-full h-28"
		:class="[
			{
				'sticky-header': isHeaderSticky,
				'mobile-menu-open': data.mobileMenuOpen,
			},
		]">
		<div class="container m-auto flex justify-between items-center w-full">
			<div class="left flex items-center justify-center gap-2 lg:gap-4">
				<Nuxt-Link
					to="/"
					class="h-[70px]">
					<div class="avatar-container h-[70px]">
						<SVGAvatar />
					</div>
					<!-- <img class="h-[70px]" src="@/assets/images/home/circle-avatar.svg" alt="avatar"/>-->
				</Nuxt-Link>
				<Nuxt-Link to="/">
					<h4
						v-show="!['sm', 'md'].includes(size)"
						class="text-1.5xl font-light pt-4 ml-[60px]">
						Jessica Turner
					</h4>
				</Nuxt-Link>
			</div>
			<template v-if="!['sm', 'md'].includes(size)">
				<nav class="right main flex justify-end items-center">
					<ul class="flex z-10 items-center">
						<li class="relative p-2">
							<a
								href="/about"
								class="animate-underline orange"
								>About</a
							>
						</li>

						<li class="relative p-2">
							<a
								href="/projects/sitezeus"
								class="animate-underline orange"
								>Projects</a
							>
						</li>

						<li class="relative p-2">
							<a
								href="/contact"
								class="animate-underline orange"
								>Contact</a
							>
						</li>
						<li class="relative p-2">
							<SvgButton
								label="Resume"
								link="https://resume.io/r/FY7HX7IvG"
								cssClass="bg-border-gradient" />
						</li>
					</ul>
				</nav>
			</template>
			<template v-else>
				<div
					class="mobile-nav-trigger ml-auto cursor-pointer fixed top-10 right-10"
					@click="
						(data.mobileMenuOpen = !data.mobileMenuOpen),
							$emit('mobileMenuClick', data.mobileMenuOpen)
					">
					<font-awesome-icon
						class="icon text-1.5xl"
						:class="
							data.mobileMenuOpen
								? 'text-light-peach hover:text-orange'
								: 'text-default-dark hover:text-dark-purple'
						"
						:icon="
							data.mobileMenuOpen ? ['fas', 'x'] : ['fas', 'bars']
						" />
				</div>
			</template>
		</div>
	</header>
</template>
<script setup>
const scrollPosition = useScroll().scrollPosition;
const scrollDirectionUp = useScroll().scrollDirectionUp;
const size = useScreenSize().size;

console.log(size);

const data = reactive({
	mobileMenuOpen: false,
});

const isHeaderSticky = computed(() => {
	if (scrollDirectionUp.value && scrollPosition.value != 0) {
		return true;
	}
	return false;
});
const onMobileMenuClick = (payload) => {
	data.mobileMenuOpen = payload;
};
</script>
