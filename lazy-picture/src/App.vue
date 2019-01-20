<template>
	<div id="app">
		<lazy-picture :sources="sources" :lazy="true"></lazy-picture>
		<lazy-picture :sources="sources" :lazy="true"></lazy-picture>
		<lazy-picture :sources="sources" :lazy="true"></lazy-picture>
		<lazy-picture :sources="sources" :lazy="true"></lazy-picture>
		<lazy-picture :sources="sources" :lazy="true"></lazy-picture>
		<lazy-picture :sources="sources" :lazy="true"></lazy-picture>
		<lazy-picture :sources="sources" :lazy="true"></lazy-picture>
		<lazy-picture :sources="sources" :lazy="true"></lazy-picture>
	</div>
</template>

<script>
import lazyPicture from "./components/LazyPicture.vue";

export default {
	name: "app",
	components: {
		lazyPicture
	},
	data() {
		return {
			sources: [
				{
					fields: {
						src: "./images/New_york_times_square-terabass.jpg",
						placeholder: "./images/rsz_new_york_times_square-terabass-small.jpg"
					},
					sys: {
						id: "1"
					}
				}
			]
		};
	}
};
</script>
