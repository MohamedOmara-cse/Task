<template>
	<button class="rounded-full text-[20px] text-[500]" @click="scrollToTop">
		Back to Top
		<i class="fa fa-arrow-up mx-2"></i>
	</button>
</template>

<script>
export default {
	name: "GoToTop",

	methods: {
		scrollToTop() {
			window.scrollTo({
				top: 0,
				behavior: "smooth",
			});
		},
	},
};
</script>
