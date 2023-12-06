<template>
	<NuxtLayout name="nonav">
		<section class="">
			<div class="flex justify-center items-center flex-col space-y-14 mt-48 container mx-auto">
				<div class="flex justify-center items-center flex-col space-y-4 w-full lg:w-1/2 mx-auto">
					<h2 class="text-dark-purple text-2xl">Let's connect!</h2>
					<p class="text-center text-dark-purple font-light">
						My virtual door is always open for a friendly chat or to
						answer any questions. Feel free to drop me a line.
					</p>
				</div>
				<form class="w-2/3 mx-auto" action="https://usebasin.com/f/8babbc19d473" method="POST">
					<div class="flex flex-row flex-nowrap justify-between items-center">
						<div class="flex flex-col items-start justify-center w-[45%] space-y-2">
							<label class="text-dark-purple" for="name"> Name: </label>
							<input class="small-label w-full px-2 py-4 rounded-lg  bg-default-light" type="name" id="name"
								name="name" required />
						</div>
						<div class="flex flex-col items-start justify-center w-[45%] space-y-2">
							<label class="text-dark-purple " for="email"> Email: </label>
							<input class="small-box w-full px-2 py-4 rounded-lg bg-default-light
]" type="email" id="email"
								name="email" required />
						</div>
					</div>
					<div class="flex flex-col items-start justify-center space-y-2 w-full my-10 space-y-1">
						<label class="text-dark-purple" for="message"> Message: </label>
						<textarea rows="5" cols="25" class="w-full px-2 py-4 large-box rounded-lg  bg-default-light"
							id="message" name="message" required />
					</div>

					<input class="submit flex justify-center button   mx-auto font-light" type="submit"
						value="Submit" />
				</form>
			</div>
		</section>
	</NuxtLayout>
</template>

<script setup>
definePageMeta({
	layout: false,
});
</script>

<style lang="scss">
@import "@/assets/scss/variables.scss";

.textarea[rows] {
	height: initial;
}

.button {



	&.submit {
		padding: 10px 16px;
		background: linear-gradient($default-light, $default-light)  padding-box, linear-gradient( 45deg, $dark-purple, $orange) border-box;
		color: $dark-purple;
		font-size: 1.2rem;
		font-weight: 300;
		transition: all .3s ease-in-out;
		border: 2px solid transparent;
		&:hover{
			background: linear-gradient($default-light, $default-light) padding-box, linear-gradient(45deg,  #FF7442, $dark-purple) border-box;

		}
	}
}

input {
	font-size: 1.2rem;
	border: 2px solid $dark-purple;
}
textarea{
	border: 2px solid $dark-purple;
}
</style>
