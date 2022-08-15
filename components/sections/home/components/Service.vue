<template>
	<li @click="toggleSelect" :class="isSelect ? 'isSelect' : 'noSelect'">
		<slot />
	</li>
</template>

<script>
export default {
	data: () => ({
		isSelect: false
	}),

	methods: {
		toggleSelect() {
			if (!this.isSelect) this.isSelect = true
			else this.isSelect = false
		}
	}
}
</script>

<style lang="scss" scoped>
li {
	font-weight: 400;
	font-size: 16px;
	line-height: 22px;

	margin: 5px;
	padding: 6px 17px;
	border-radius: 5px;
	list-style: none;
	user-select: none;
	cursor: pointer;
	transition: all .3s ease;


}

.noSelect {
	border: 1px solid #FFFFFF;

	&:hover {
		background: rgba(255, 255, 255, 0.2);
	}
}

.isSelect {
	background: #CB2B2E;
	border: 1px solid #CB2B2E;
	border-radius: 5px;
}
</style>