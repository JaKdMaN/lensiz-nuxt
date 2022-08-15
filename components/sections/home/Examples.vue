<template>
	<section class="examples">
		<b-container>
			<h2 class="examples__headline">Примеры наших работ</h2>
			<div v-swiper:examplesSwiper="examplesSwiperOptions">
				<div class="swiper-wrapper">
					<div class="swiper-slide" v-for="example in examples" :key="example.id">
						<div class="slide-block">
							<div class="slide-image">
								<img :src="example.image" alt="image">
							</div>
							<p v-html="example.title" class="slide-title" />
						</div>
					</div>
				</div>
			</div>
		</b-container>
		<ls-button class="examples__button">Рассчитать стоимость</ls-button>
	</section>
</template>

<script>
import LsButton from '~/components/LsButton.vue'
export default {
	components: { LsButton },
	name: 'Examples',
	data: () => ({
		examplesSwiperOptions: {
			slidesPerView: 4,
			slidesPerGroup: 1,
			spaceBetween: 20,
			loop: true,
			breakpointsInverse: true,
			breakpoints: {
				1: {
					slidesPerView: 1,
					slidesPerGroup: 1,
				},
				700: {
					slidesPerGroup: 1,
					slidesPerView: 3,
					spaceBetween: 20,
				},
				1024: {
					slidesPerGroup: 1,
					slidesPerView: 4,
					spaceBetween: 20,
				},
			},
		},
		examples: [
			{
				id: 1,
				image: require('@/assets/images/example1.png'),
				title: 'Спецпошив для <strong>“ГорСтрой”</strong>'
			},
			{
				id: 2,
				image: require('@/assets/images/example2.png'),
				title: 'Спецпошив для <strong>“ГорСтрой”</strong>'
			},
			{
				id: 3,
				image: require('@/assets/images/example3.png'),
				title: 'Спецпошив для <strong>“ГорСтрой”</strong>'
			},
			{
				id: 4,
				image: require('@/assets/images/example4.png'),
				title: 'Спецпошив для <strong>“ГорСтрой”</strong>'
			}
		]
	})

}
</script>

<style lang="scss" scoped>
.examples {
	margin-top: 200px;

	&__headline {
		font-weight: 700;
		font-size: 45px;
		line-height: 55px;

		color: #082151;
	}

	&__button {
		margin-top: 60px;
		padding: 20px 80px;
	}
}

.swiper-wrapper {
	margin-top: 60px;
}

.slide-block {
	padding: 25px;
	box-shadow: 0px 0px 20px rgba(56, 56, 56, 0.1);
	border-radius: 10px;
}

.slide-image {
	max-width: 100%;
	max-height: 100%;

	img {
		width: 100%;
		height: 100%;
		object-fit: cover;
		object-position: center;
	}
}

.slide-title {
	margin-top: 20px;
	font-weight: 400;
	font-size: 14px;
	line-height: 32px;
	text-align: center;
}
</style>