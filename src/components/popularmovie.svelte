<script>
  export let popular;
  import MovieCard from "./movieCard.svelte";

</script>
<h3>Popular Movies</h3>
<div class="popular-movies">
  {#each popular as movie}
    <MovieCard {movie}/>
  {/each}
</div>
<style>
  h3{
    padding: 0 1rem;
  }
  .popular-movies{
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    grid-row-gap: 2rem;
    grid-column-gap: 1rem;
  }
</style>
