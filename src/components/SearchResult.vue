<template>
	<div class="result">
		<i class="fa fa-star fa32 pointer result-favorite" @click="star(result.id)" :class="{starred: this.$store.state.search.starred.includes(result.id)}"></i>
		<router-link :to="{name: 'market', params: {id: result.id}}">{{result.name}}</router-link>
		<br />
		<address>Babelsberger Straße 16, Potsdam</address>
	</div>
</template>

<script>
	export default {
		name: 'SearchResult',
		props: {
			result: {
				type: Object,
				required: true
			}
		},
		methods: {
			star(id) {
				this.$store.dispatch('search/star', id);
			}
		}
	};
</script>