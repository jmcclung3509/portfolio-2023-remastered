<template>
	<div class="mobile-menu fixed flex flex-col flex-1 lg:hidden md:w-1/2 p-10 overflow-auto space-y-4">
		<ul class="space-y-4">
			<li class="relative p-2">
							<a href="/about" class="animate-underline orange"
								>About</a>
						</li>

						<li class="relative p-2">
							<a href="/projects/sitezeus" class="animate-underline orange"
								>Projects</a>
						</li>

						<li class="relative p-2" >
							<a href="/contact" class="animate-underline orange"
								>Contact</a>
						</li>
						<li class="relative p-2" >
							<a href="https://resume.io/r/FY7HX7IvG" target="_blank" class="animate-underline orange"
								>Resume</a>
						</li>
			<li>
				<nuxt-link class="button hollow" to="https://resume.io/r/FY7HX7IvG" >Resume</nuxt-link></li>

		</ul>
	</div>

</template>