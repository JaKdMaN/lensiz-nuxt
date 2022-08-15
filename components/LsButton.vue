<template>
	<div class="button-wrapper">
		<button class="ls-button">
			<slot />
		</button>
	</div>

</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.button-wrapper {
	text-align: center;
}

.ls-button {
	display: inline-block;
	font-size: 24px;
	line-height: 1;

	color: #FFFFFF;

	padding: 20px 100px;
	border: none;
	font: inherit;
	background-color: #CB2B2E;
	border-radius: 5px;
	cursor: pointer;
	transition: all .3s ease-in-out;

	&:hover {
		background: #F5575A;
	}

	&:focus {
		background: #A90C0F;
	}
}
</style>