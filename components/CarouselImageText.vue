<template>
	<div
		class="image-text-carousel flex flex-col-reverse lg:flex-row lg:items-start justify-center w-full  lg:space-x-14 container">
		<div
			class="image-container w-full lg:w-1/2 mx-auto rounded-2xl relative pt-14 lg:pt-0">
			<client-only>
				<Swiper
					:modules="data.modules"
					:space-between="10"
					:navigation="{
						nextEl: '.custom-next',
						prevEl: '.custom-prev',
					}"
					@slideChange="onSlideChange"
					@swiper="onSwiper">
					<swiper-slide
						v-for="(item, i) in props.images"
						:key="i">
						<template v-if="item.type === 'video/mp4'">
							<video
								class="video rounded-2xl max-h-[600px] mx-auto"
								autoplay="autoplay"
								loop="loop"
								muted="muted">
								<source
									class=""
									:src="item.src"
									type="video/mp4" />
							</video>
						</template>
						<template v-else>
							<img
								:src="item.src"
								:alt="item.alt" />
						</template>
					</swiper-slide>
					<div class="custom-navigation">
						<div
							v-show="data.currentIndex > 0"
							class="custom-prev"></div>
						<div
							v-show="data.currentIndex < props.images.length - 1"
							class="custom-next "></div>
					</div>
				</Swiper>
			</client-only>
		</div>
		<div class="text-container flex w-full lg:w-1/2 items-start">
			<div
				class="generic-text flex flex-col space-y-4 text-center mb-7 lgmb-0 md:text-left w-full">
				<transition
					name="fadeIn"
					mode="out-in">
					<slot :realIndex="data.realIndex" />
				</transition>
			</div>
		</div>
	</div>
</template>
<script setup>
import { Swiper } from "swiper/vue";
import { SwiperSlide } from "swiper/vue";

import { Navigation } from "swiper/modules";

import "swiper/scss";
import "swiper/scss/navigation";

const props = defineProps({
	images: Array,
});

const data = reactive({
	modules: [Navigation],
	currentIndex: 0,
	realIndex: 0,
	swiperAutoplay: false,
});
const onSwiper = (swiper) => {
	console.log(swiper);
	data.swiperAutoplay = swiper.autoplay;
};

const onSlideChange = (swiper) => {
	console.log(swiper);
	data.currentIndex = swiper.activeIndex;
	data.realIndex = swiper.realIndex;
};
</script>

<style lang="scss">
@import "@/assets/scss/variables.scss";
.custom-navigation {
	display: flex;
	justify-content: center;

	position: relative;
	width: 100%;
	z-index: 10;
	margin-top: 30px;
	.custom-next,
	.custom-prev {
		display: inline;
		cursor: pointer;
		&:before, &:after {
			font-weight: 300;
			content: "";
			position: absolute;
			bottom: 0;
			z-index: 10;
			color: $dark-purple;
			font-size: 1rem;
			transition: all 0.3s;
		}
		&:hover {
			&:before, &:after {
				color: $orange;
			}
		}
		&.custom-next {
			&:before {

				content: "Next";
				right: 100px;
			}
			&:after{
				font-family: "Material Symbols Outlined";
				content: "arrow_forward";
				right: 70px;
			}

		}
		&.custom-prev {
			&:before {
				content: "Previous";
				left: 100px;

			}
			&:after{
				font-family: "Material Symbols Outlined";
				content: "arrow_back";
				left: 70px;
			}
		}
	}
}

</style>
