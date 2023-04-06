<template>
	<nav class="flex justify-between w-full py-10">
		<div>
			<h1 class="text-balck font-bold text-[22px] text-[700]">LOGO</h1>
		</div>
		<div class="flex items-center gap-5">
			<a
				:class="{ 'text-yellow-500': activeTab === '', 'text-balck': activeTab !== '' }"
				href="/"
				class="hover:text-yellow-500 md:text-[18px] transition-colors duration-200"
				>Home</a
			>
			<a
				:class="{ 'text-yellow-500': activeTab === 'about', 'text-balck': activeTab !== 'about' }"
				href="/about"
				class="hover:text-yellow-500 md:text-16ppx] transition-colors duration-200"
				>About</a
			>
			<a
				:class="{ 'text-yellow-500': activeTab === 'projects', 'text-balck': activeTab !== 'projects' }"
				href="/projects"
				class="hover:text-yellow-500 md:text-[18px] transition-colors duration-200"
				>Projects</a
			>
			<a
				:class="{ 'text-yellow-500': activeTab === 'contact', 'text-balck': activeTab !== 'contact' }"
				href="/contact"
				class="hover:text-yellow-500 md:text-18px] transition-colors duration-200"
				>Contact</a
			>
		</div>
	</nav>
</template>

<script>
export default {
	data() {
		return {
			activeTab: "home",
		};
	},
	mounted() {
		this.activeTab = window.location.pathname.split("/")[1];
	},
};
</script>
