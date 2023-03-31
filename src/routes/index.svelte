<script context="module">
  export async function load({ fetch }) {
    const res = await fetch(
      `https://api.themoviedb.org/3/movie/popular?api_key=10bf74d13b6be6fb06af731b7e1ed63f&language=en-US&page=1`
      );
    const data = await res.json();
    if (res.ok){
      return {
        props: { popular: data.results }
      };
    }
  }
</script>
<script>
  import PopularMovies from '../components/popularmovie.svelte';
  import  SearchMovie from '../components/searchMovies.svelte';
  import {fly} from 'svelte/transition';
  export let popular;
</script>
<section in:fly={{y:50, duration: 500, delay: 500}} out:fly={{duration:500}}>
  <SearchMovie />
  <PopularMovies {popular}/>
</section>