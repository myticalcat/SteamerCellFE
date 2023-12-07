
<script>
    export let performSearch;
    let name = '';
    let brand = '';
    let minRAM = 4;
    let maxRAM = 16;
    let os = '';
    let priceMin = 100;
    let priceMax = 2000;
    let storageMin = 128;
    let storageMax = 1024;
    let hasWifi = false;
    let has4g = false;
</script>

<div class="input">
    <input type="text" bind:value={name} placeholder="Name" />
    <input type="text" bind:value={brand} placeholder="Brand" />
    <label>
      Min RAM (GB):
      <input type="range" bind:value={minRAM} min="0" max="64" />
      {minRAM}
    </label>
    <label>
      Max RAM (GB):
      <input type="range" bind:value={maxRAM} min="0" max="64" />
      {maxRAM}
    </label>
    <label>
      Operating System:
      <select bind:value={os}>
        <option value="">Select OS</option>
        <option value="Windows">Windows</option>
        <option value="macOS">macOS</option>
        <option value="Linux">Linux</option>
        <option value="ChromeOS">ChromeOS</option>
        <option value="Android">Android</option>
        <option value="iOS">iOS</option>
      </select>
    </label>
    <label>
      Min Price:
      <input type="range" bind:value={priceMin} min="0" max="5000" step="50" />
      {priceMin}
    </label>
    <label>
      Max Price:
      <input type="range" bind:value={priceMax} min="0" max="5000" step="50" />
      {priceMax}
    </label>
    <label>
      Min Storage (GB):
      <input type="range" bind:value={storageMin} min="0" max="2000" />
      {storageMin}
    </label>
    <label>
      Max Storage (GB):
      <input type="range" bind:value={storageMax} min="0" max="2000" />
      {storageMax}
    </label>
    <label>
      <input type="checkbox" bind:checked={hasWifi} />
      WiFi
    </label>
    <label>
      <input type="checkbox" bind:checked={has4g} />
      4G
    </label>
    <button on:click={() => performSearch({ name, brand, minRAM, maxRAM, os, priceMin, priceMax, storageMin, storageMax, hasWifi, has4g })}>Search</button>
  </div>
  
  <style>
    .input {
      margin: 5px auto; /* This will center the element horizontally if it has a defined width */
      padding: 10px;
      background-color: #f0f0f0; /* Light grey */
      text-align: center; /* This will center the text inside the input element */
    }
  
    /* If you want to center the labels and input fields within .input */
    label, input, button {
      margin-left: auto;
      margin-right: auto;
    }

  </style>
  