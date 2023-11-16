<template>
	<section
			id="projects"
			class="section projects bg-light-peach pb-52">
			<div class="container mx-auto space-y-14 py-36 px-20">
				<h2 class="text-2xl text-default-dark ml-20">Projects</h2>
				<div
					class="projects-container flex flex-col justify-center items-center md:flex-row md:flex-wrap">
					<FlipBox
						title="SiteZeus"
						link="/projects/sitezeus"
						slug="sitezeus"
						imageSrc="static/images/pages/home/sitezeus-homepage.png"
						:tagArray="['Vue', 'Nuxt', 'Tailwind']">
					</FlipBox>
					<FlipBox
						title="Insites"
						link="/projects/insites"
						slug="insites"
						imageSrc="/static/images/pages/home/insites-homepage.png"
						:tagArray="['WordPress', 'PHP', 'Vanilla JavaScript']">
					</FlipBox>
					<FlipBox
						title="Nick's Restaurant"
						link="projects/nicks"
						slug="nicks"
						imageSrc="/static/images/pages/home/nicks-homepage.png"
						:tagArray="['Vue', 'Nuxt', 'Tailwind']">
					</FlipBox>
					<FlipBox
						title="Sticky Notes App"
						link="projects/sticky-notes-app"
						slug="sticky-notes"
						imageSrc="/static/images/pages/home/sticky-notes-app.png"
						:tagArray="['React', 'Bootstrap', 'Figma']">
					</FlipBox>
					<FlipBox
						title="Quizzical"
						link="/projects/quizzical"
						slug="quizzical"
						imageSrc="/static/images/pages/home/quizzial.png"
						:tagArray="[
							'React',
							'React hooks',
							'API',
							'Figma',
						]"></FlipBox>

					<FlipBox
						title="Portfolio"
						link="projects/portfolio"
						slug="quizzical"
						imageSrc="/static/images/pages/home/portfolio.png"
						:tagArray="['Vue', 'Nuxt', 'Tailwind']">
					</FlipBox>
				</div>
			</div>
		</section>
</template>

<script setup>

const route = useRoute();
const size = useScreenSize().size;
const { isMobile } = useScreenSize();



const data = reactive({
	mobileMenuOpen: false,
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
