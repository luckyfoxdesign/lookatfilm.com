<script>
	import { filmFirstData } from "../../routes/films/_store/store"

	export let id
	export let title
	export let src
	export let year
	export let genres
	export let kinopoiskRaiting

	let filmInfo = {
		id: id,
		title: title,
		src: src,
		kinopoiskRaiting: kinopoiskRaiting,
		year: year,
		genres: genres,
	}

	function addFilmInfoToStore() {
		filmFirstData.update((e) => (e = filmInfo))
	}
</script>

<style>
	.film {
		display: grid;
		grid-template-columns: auto 1fr;
		grid-template-rows: auto;
	}
	.film-poster {
		width: 78px;
		height: 116px;
		overflow: hidden;
		border-radius: 4px;
	}
	img {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}
	.film-info {
		display: grid;
		grid-template-columns: 1fr;
		grid-template-rows: auto auto auto;
		row-gap: 4px;
		align-self: start;
		margin-left: 16px;
	}
	.film-title {
		font-weight: 700;
	}
	.film-genres {
		color: var(--Gray75);
	}
	.film-year {
		color: var(--Gray75);
	}
	a {
		text-decoration: none;
		color: var(--Gray33);
	}
</style>

<a rel="prefetch" href="films/{id}" class="film" on:click={addFilmInfoToStore}>
	<div class="film-poster"><img {src} alt={title} /></div>
	<div class="film-info">
		<div class="film-title">{title}</div>
		<div class="film-year">{year}</div>
		<div class="film-genres">{genres}</div>
	</div>
</a>
