<template>
	<footer class="mt-[100px]">
		<div class="flex flex-col lg:flex-row items-center gap-10 justify-between">
			<h2 class="font-[#2F2F2F] text-[24px] lg:text-[36px] text-[500]">Let's Connect</h2>
			<Social />
			<GoBackButton />
		</div>
	</footer>
</template>

<script>
import GoBackButton from "./goBackButton.vue";
import Social from "./social.vue";
export default {
	components: { GoBackButton, Social },
	name: "Footer",
};
</script>
