<template>
	<div class="py-10">
		<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css" />

		<h1 class="font-[600]">Our Projects</h1>
		<nav class="w-[80%]">
			<ul class="flex justify-between w-full mt-[40px]">
				<li
					class="text-[16px] md:text-[24px] lg:text-[32px]"
					@click="setActiveTab('Web Design')"
					:class="{ 'is-active': activeTab === 'Web Design' }"
				>
					Web Design
				</li>
				<li
					class="text-[16px] md:text-[24px] lg:text-[32px]"
					@click="setActiveTab('Mobile Design')"
					:class="{ 'is-active': activeTab === 'Mobile Design' }"
				>
					Mobile App Design
				</li>
				<li
					class="text-[16px] md:text-[24px] lg:text-[32px]"
					@click="setActiveTab('Freebies')"
					:class="{ 'is-active': activeTab === 'Freebies' }"
				>
					Freebies
				</li>
			</ul>
		</nav>

		<section class="w-full my-10 gap-x-20 gap-y-20 grid lg:grid-cols-2" v-if="activeTab === 'Web Design'">
			<card v-for="item in webData" :key="item.title" :imageSrc="item.imageSrc" :title="item.title" />
		</section>

		<section class="w-full my-10 gap-x-20 gap-y-20 grid lg:grid-cols-2" v-if="activeTab === 'Mobile Design'">
			<card v-for="item in mobileData" :key="item.title" :imageSrc="item.imageSrc" :title="item.title" />
		</section>

		<section class="w-full my-10 gap-x-20 gap-y-20 grid lg:grid-cols-2" v-if="activeTab === 'Freebies'">
			<card v-for="item in freebiesData" :key="item.title" :imageSrc="item.imageSrc" :title="item.title" />
		</section>

		<div
			class="w-full h-[100px] lg:h-[200px] mt-[150px] bg-[#EEBF63] rounded-[25px] flex items-center justify-between lg:px-20 p-5"
		>
			<h2 class="text-white text-[20px] lg:text-[48px] text-[600]">
				Interested working
				<span class="text-white text-[20px] lg:text-[48px] text-[600]">with me?</span>
			</h2>
			<a
				href="https://atw.ltd/"
				class="bg-white flex min-w-[150px] md:min-w-[300px] items-center justify-center text-[16px] lg:text-[32px] lg:h-[80px] rounded-[10px] p-3 lg:rounded-[10px] lg:p-10"
			>
				<i class="fa fa-envelope-o mr-[10px]"></i>
				Email Me
			</a>
		</div>
		<Footer></Footer>
	</div>
</template>
plugins/fontawsome.js
<script>
import card from "../components/card.vue";
import Footer from "../components/footer.vue";
export default {
	components: {
		card,
		Footer,
	},
	data() {
		return {
			webData: [
				{ imageSrc: "image.png", title: "Minify - Web Design" },
				{ imageSrc: "kepper.png", title: "Keeper - Soccer Site" },
				{ imageSrc: "Ant.png", title: "Ant - Personal Portofolio" },
				{ imageSrc: "Lumy.png", title: "Lumy - Dashboard UI Kit" },
			],
			mobileData: [
				{ imageSrc: "kepper.png", title: "Keeper - Soccer Site" },
				{ imageSrc: "Ant.png", title: "Ant - Personal Portofolio" },
				{ imageSrc: "image.png", title: "Minify - Web Design" },
				{ imageSrc: "Lumy.png", title: "Lumy - Dashboard UI Kit" },
			],
			freebiesData: [
				{ imageSrc: "kepper.png", title: "Keeper - Soccer Site" },
				{ imageSrc: "image.png", title: "Minify - Web Design" },
				{ imageSrc: "Ant.png", title: "Ant - Personal Portofolio" },
				{ imageSrc: "Lumy.png", title: "Lumy - Dashboard UI Kit" },
			],
			activeTab: "Web Design",
		};
	},
	methods: {
		setActiveTab(tab) {
			this.activeTab = tab;
		},
	},
};
</script>
<style scoped>
.is-active {
	color: #eebf63;
	border-bottom: 4px solid #eebf63;
	line-height: 2em;
}
li {
	font-style: normal;
	font-weight: 600;
	line-height: 2em;
	color: #828282;
	cursor: pointer;
}
.white-color {
	color: #fff;
	border-block-color: #000;
}
</style>
