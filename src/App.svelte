<script>
  import SearchForm from './SearchForm.svelte';

  let search = (searchParams) => {
    console.log('Searching for devices with the following parameters:', searchParams);
  }
  console.log(typeof search)
</script>

<div class="banner">
	<h1>Kukusan Cell</h1>
  </div>
  <div class="container">
	<SearchForm performSearch={search} />
	<div class="output">
	</div>
</div>  

<style>
  .banner {
      background-color: #333; /* Dark grey */
      color: white;
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
      background-color: #d0d0d0; /* Medium grey */
    }
</style>
