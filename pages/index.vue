<template>
	<div>
		<Main />
		<About />
		<Examples />
		<Discounts />
	</div>

</template>

<script>
import Main from '~/components/sections/home/Main.vue';
import About from '~/components/sections/home/About.vue';
import Examples from '~/components/sections/home/Examples.vue';
import Discounts from '~/components/sections/home/Discounts.vue';
export default {
	name: "IndexPage",
	components: { Main, About, Examples, Discounts }
}
</script>
