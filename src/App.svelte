<script>
import SearchForm from './SearchForm.svelte';
let kukusanCell = "https://cdn.discordapp.com/attachments/790868959800197151/1182273948537344010/kukusan_cell.gif?ex=6584196a&is=6571a46a&hm=c109f6cba71b78f9aaaf964112505872ba523e7935bde2624c5dd7c8bc2a132d&";
let searching = false
let search = (searchParams) => {
    console.log('Searching for devices with the following parameters:', searchParams);
	searching = !searching
}

</script>

<div>
	<div class="banner">
		<img src={kukusanCell} alt="Kukusan Cell" class="full-width-image">
	</div>
	<div class="container">
		<div class="input-container">
			search
			<SearchForm performSearch={search} />
		</div>
		<div class="output">
			{#if searching}
				<img src="https://web.archive.org/web/20091021201333/http://www.geocities.com/judika3/RangerSearchingXLClearAnimatedGIF.gif" alt="Loading..." class="loading-image">
				<h1>please wait...</h1>
			{/if}
		</div>
	</div>
</div>

<style>

:global(body){
	background: linear-gradient(to bottom, #ffafcc, #a2d2ff);
}
.banner {
    background-color: rgba(255, 255, 255, 0.5);
    padding: 10px;
    text-align: center;
}

.container {
    display: flex;
    padding: 10px;
}

.output {
    flex: 1;
    margin: 5px;
    padding: 10px;
    width: 50%;
}

.output {
    background-color: rgba(255, 255, 255, 0.5);
}

.full-width-image {
    width: 30vw;
    height: 7vw;
    object-fit: cover; 
}

.input-container{
	padding: 5px 5px 5px 5px;
	background-color: #0058f0;
	color: white;
}
</style>
