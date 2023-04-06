<template>
	<div class="container mx-auto">
		<h1 class="text-3xl font-bold mb-5">Movie Search</h1>
		<form @submit.prevent="searchMovies">
			<div class="flex items-center mb-5">
				<label for="search" class="mr-3">Search:</label>
				<input type="text" id="search" v-model="searchTerm" class="border border-gray-400 px-3 py-2 rounded-lg w-64" />
				<button
					type="submit"
					class="bg-blue-500 text-white px-5 py-2 ml-3 rounded-lg hover:bg-blue-600 transition-colors duration-200"
				>
					Search
				</button>
			</div>
		</form>
		<div v-if="movies" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-5">
			<div v-for="movie in movies" :key="movie.imdbID" class="p-5 bg-white shadow-md rounded-md">
				<img :src="movie.Poster" :alt="movie.Title" class="w-full h-64 object-cover mb-3" />
				<h2 class="text-xl font-bold">{{ movie.Title }}</h2>
				<p class="text-gray-600">{{ movie.Year }}</p>
			</div>
		</div>
		<p v-if="errorMessage" class="text-red-500">{{ errorMessage }}</p>
	</div>
</template>

<script>
export default {
	data() {
		return {
			searchTerm: "",
			movies: [],
			errorMessage: null,
		};
	},
	methods: {
		async searchMovies() {
			try {
				const response = await fetch(`https://www.omdbapi.com/?s=${this.searchTerm}&apikey=3eeafb`).then((res) =>
					res.json()
				);
				if (response.Response == "True") {
					this.movies = response.Search;
					this.errorMessage = null;
				} else {
					this.movies = null;
					this.errorMessage = response.Error;
				}
			} catch (error) {
				console.error(error);
				this.movies = null;
				this.errorMessage = "An error occurred while fetching movies. Please try again later.";
			}
		},
	},
};
</script>

<style>
.container {
	max-width: 1200px;
	padding: 0 20px;
}
</style>
