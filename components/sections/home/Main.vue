<template>
	<main class="main-section" id="welcome">
		<div v-swiper:mainSwiper="swiperMainOptions">
			<div class="swiper-wrapper">
				<div class="swiper-slide" v-for="banner in banners" :key="banner.id"
					:style="{ 'background-image': `url(${banner.backUrl})` }">
					<b-container class="swiper-block">
						<h1 class="swiper-headline">{{ banner.title }}</h1>
						<p class="swiper-description">{{ banner.description }}</p>
						<ls-button class="main-button">Перейти в каталог</ls-button>
					</b-container>
				</div>
			</div>
			<div class="swiper-pagination swiper-pagination-bullets"></div>
		</div>
	</main>
</template>

<script>
import LsButton from '~/components/LsButton.vue';
export default {
	name: "Main",
	data() {
		LsButton
		return {
			banners: [
				{
					id: 0,
					title: 'ЛенСИЗ — Безопасность Вашего труда',
					description: 'Наши товары имеют все необходимые сертификаты соответствия',
					backUrl: require('@/assets/images/banner1.png')
				},
				{
					id: 1,
					title: 'Индивидуальный пошив, с фирменным стилем',
					description: 'Клиент всегда запомнит ту компанию, которая выделяется своим стилем, сильной маркетинговой и социальной составляющими',
					backUrl: require('@/assets/images/banner2.png')
				},
				{
					id: 2,
					title: 'Интернет-магазин готовой продукции',
					description: 'Каталог компании насчитывает более 3000 позиций товаров, необходимых для защиты здоровья и жизни человека в процессе работы',
					backUrl: require('@/assets/images/banner3.png')
				}

			],

			swiperMainOptions: {
				pagination: {
					el: ".swiper-pagination",
					type: "bullets",
					clickable: true,
				},
			}
		}
	}

};
</script>

<style lang="scss" scoped>
.main-button {
	margin-top: 60px;
	text-align: left;
}

.swiper-wrapper {
	max-width: 100%;
	height: 100vh;
}

.swiper-slide {
	width: 100%;
	height: 100%;
	background-size: cover;
	background-position: center;
	display: flex;
	align-items: center;

	@media screen and (max-width: 998px) {
		background-position: 70%;
	}
}

.swiper-headline {
	font-weight: 700;
	font-size: 60px;
	line-height: 70px;

	color: #FFFFFF;
}

.swiper-description {
	margin-top: 30px;
	font-weight: 400;
	font-size: 32px;
	line-height: 44px;

	color: #FFFFFF;
}
</style>
