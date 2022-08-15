<template>
	<section class="discounts" id="discounts">
		<div class="discounts__back" />
		<b-container>
			<b-row>
				<b-col cols="12" md="5">
					<img src="@/assets/images/Logo.svg" alt="logo" class="discounts__logo">
					<h2 class="discounts__headline">Скидка 10% на заказ с сайта</h2>
				</b-col>
				<b-col cols="12" md="7" class="services pl-md-5">
					<h3 class="services__headline">Что Вас интересует?</h3>
					<ul class="services__items">
						<Service v-for="el in serviceItem" :key="el">
							{{ el }}
						</Service>
					</ul>
					<h3 class="services__headline--additional">дополнительные услуги</h3>
					<div class="services__checkboxes">
						<CheckBox class="services__checkboxes--checkbox" v-for="el in checkBoxes" :key="el">{{ el }}
						</CheckBox>
					</div>
				</b-col>
			</b-row>
		</b-container>

	</section>
</template>

<script>
import Service from './components/Service';
import CheckBox from './components/CheckBox.vue';
export default {
	name: "discounts",

	data: () => ({

		serviceItem: [
			"Спецодежда",
			"Спецобувь",
			"СИЗ",
			"Защита для рук",
			"Инвентарь",
			"Текстиль",
			"Хозтовары"
		],

		checkBoxes: ['Индивидуальный пошив', 'Готовая продукция', 'Нанесение логотипа']
	}),

	components: { Service, CheckBox }
}
</script>

<style lang="scss" scoped>
.discounts {
	margin-top: 200px;
	position: relative;
	z-index: 10;
	background: #082151;

	&__back {
		position: absolute;
		max-width: 630px;
		width: 100%;
		height: 100%;
		top: 0;
		left: 0;
		z-index: -1;
		background: url("@/assets/images/discounts.png") no-repeat;
		background-size: cover;
	}

	&__logo {
		margin-top: 100px;
	}

	&__headline {
		margin-top: 15px;
		font-weight: 700;
		font-size: 45px;
		line-height: 55px;

		color: #FFFFFF;
	}

	.services {
		margin-top: 50px;
		color: #FFFFFF;

		&__headline {
			font-weight: 700;
			font-size: 20px;
			line-height: 80px;
			text-transform: uppercase;

			&--additional {
				margin-top: 40px;
			}
		}

		&__items {
			display: flex;
			flex-wrap: wrap;
			padding: 0;
		}

		&__item {
			font-weight: 400;
			font-size: 16px;
			line-height: 22px;

			margin: 5px;
			padding: 6px 17px;
			border: 1px solid #FFFFFF;
			border-radius: 5px;
			list-style: none;
			user-select: none;
			cursor: pointer;
		}

		&__checkboxes {
			display: flex;
			margin-top: 25px;

			&--checkbox {
				margin-right: 15px;
			}
		}
	}

}
</style>