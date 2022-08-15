
<template>
	<label class="custom-checkbox" :class="['some__label', { 'error-chk': checkFail }]">
		<input type="checkbox" value="value-1" v-model="personalData" :class="{ 'error-chk': checkFail }">
		<span :class="{ 'error-chk': checkFail }">
			<slot />
		</span>
	</label>
</template>

<script>
export default {

	data: () => ({
		personalData: false,
		checkFail: false
	})


}
</script>

<style lang="scss" scoped>
.custom-checkbox {

	& input {
		position: absolute;
		z-index: -1;
		opacity: 0;
	}

	& span {
		display: inline-flex;
		align-items: center;
		user-select: none;
	}

	/* создание в label псевдоэлемента before со следующими стилями */
	& span:before {
		content: '';
		display: inline-block;
		width: 1em;
		height: 1em;
		flex-shrink: 0;
		flex-grow: 0;
		border: 1px solid #adb5bd;
		border-radius: 0.25em;
		margin-right: 0.5em;
		background-repeat: no-repeat;
		background-position: center center;
		background-size: 50% 50%;
		transition: background-color .3s ease;
	}

	/* стили для чекбокса, находящегося в состоянии checked */
	& input:checked+span::before {
		border-color: #CB2B2E;
		background-color: #CB2B2E;
		background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 8 8'%3e%3cpath fill='%23fff' d='M6.564.75l-3.59 3.612-1.538-1.55L0 4.26 2.974 7.25 8 2.193z'/%3e%3c/svg%3e");
	}

	/* стили для чекбокса, находящегося в состоянии disabled */
	& input:disabled+span::before {
		background-color: #e9ecef;
	}

	& input:not(:disabled):not(:checked)+span:hover::before {
		background: rgba(255, 255, 255, 0.2);
	}

}
</style>