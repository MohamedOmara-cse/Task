<template>
	<div>
		<div class="mx-auto px-5 lg:px-[160px]">
			<Nav />
			<slot />
		</div>
	</div>
</template>

<script>
import Nav from "~/components/nav.vue";
import Footer from "../components/footer.vue";

export default {
	name: "Layout",
	components: { Footer, Nav },
};
</script>
