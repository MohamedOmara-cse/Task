<template>
	<div class="card">
		<img :src="imageSrc" alt="Card image" />
		<h1 class="card-title">{{ title }}</h1>
		<div class="flex gap-8">
			<h2><font-awesome-icon :icon="['fas', 'eye']" /> View Study Cass</h2>
			<h2><font-awesome-icon :icon="['fas', 'eye']" /> Live Preview</h2>
		</div>
	</div>
</template>

<script>
export default {
	props: {
		imageSrc: {
			type: String,
			required: true,
		},
		title: {
			type: String,
			required: true,
		},
	},
};
</script>

<style>
.card {
	border-radius: 0.25rem;
}

.card img {
	border-radius: 25px;
	width: 100%;
}

.card-title {
	font-size: 1.25rem;
	margin-top: 0.5rem;
}
</style>
