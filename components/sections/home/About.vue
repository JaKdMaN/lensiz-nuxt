<template>
	<section class="about" id="about">
		<b-container>
			<b-row>
				<b-col cols="12" md="5">
					<div class="about__image">
						<img src="@/assets/images/about.png" alt="about">
					</div>
					<nuxt-link to="/" class="d-inline-flex align-items-center about__link">
						О компании
						<i class="material-icons-round about__link--arrow">arrow_right_alt</i>
					</nuxt-link>
				</b-col>
				<b-col cols="12" md="7" class="pl-md-5">
					<h2 class="about__headline">
						<span class="about__headline--blue">Компания ЛенСИЗ - </span>
						услуги по пошиву спецодежды для защиты здоровья
					</h2>
					<b-row class="about__info info">
						<b-col cols="12" md="3" v-for="item in info" :key="item.title">
							<h3 class="info__headline">{{ item.title }}</h3>
							<p class="info__description">{{ item.description }}</p>
						</b-col>
					</b-row>
				</b-col>
			</b-row>
		</b-container>
	</section>
</template>

<script>
export default {
	data: () => ({
		info: [
			{
				title: '118',
				description: 'сотрудников в компании'
			},
			{
				title: '10',
				description: 'лет опыта в производстве'
			},
			{
				title: '3000',
				description: 'позиций товаров'
			},
			{
				title: '38',
				description: 'партнеров по всей России'
			}
		]
	}),
}
</script>

<style lang="scss" scoped>
.about {
	margin-top: 200px;

	&__image {
		max-width: 600px;
		max-height: 400px;
		border-radius: 2px;

		img {
			width: 100%;
			height: 100%;
			object-fit: cover;
			object-position: center;
		}
	}

	&__link {
		margin-top: 30px;
		font-family: 'Arial';
		font-style: normal;
		font-weight: 400;
		font-size: 40px;
		line-height: 32px;

		color: #082151;

		&:hover &--arrow {
			transform: translateX(15px);
		}

		&--arrow {
			font-size: inherit;
			margin-left: 20px;

			transition: all .3s ease;
		}
	}

	&__headline {
		font-weight: 700;
		font-size: 45px;
		line-height: 55px;

		&--blue {
			font: inherit;
			color: #1F4A9C;
		}
	}

	.info {
		margin-top: 80px;

		@media screen and (max-width: 998px) {
			margin-top: 40px;
		}

		&__headline {
			font-weight: 700;
			font-size: 45px;
			line-height: 55px;

			color: #CB2B2E;
		}

		&__description {
			font-weight: 400;
			font-size: 20px;
			line-height: 32px;

			color: #202020;
		}
	}
}
</style>