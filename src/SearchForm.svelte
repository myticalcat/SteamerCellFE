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
    <input type="text" bind:value={name} placeholder="Name" class="block-container" />
    <input type="text" bind:value={brand} placeholder="Brand" class="block-container"/>
    <label>
        <div class="flex-container">
            <p class="prop-name">Min RAM (GB):</p>
        </div>
        <div class="flex-container">
            <input type="range" bind:value={minRAM} min="0" max="64" />
            <p>{minRAM}</p>
        </div>
    </label>
    <label>
        <div class="flex-container">
            <p class="prop-name">Max RAM (GB):</p>
        </div>
        <div class="flex-container">
            <input type="range" bind:value={maxRAM} min="0" max="64" />
            <p>{maxRAM}</p>
        </div>
    </label>
    <label>
        Operating System:
        <select bind:value={os}>
            <option value="">Select OS</option>
            <option value="Android">Android</option>
            <option value="iOS">iOS</option>
        </select>
    </label>
    <label>
        <div class="flex-container">
            <p class="prop-name">Min Price:</p>
        </div>
        <div class="flex-container">
            <input type="range" bind:value={priceMin} min="0" max="5000" step="1" />
            <p>{priceMin}</p>
        </div>
    </label>
    <label>
        <div class="flex-container">
            <p class="prop-name">Max Price:</p>
        </div>
        <div class="flex-container">
            <input type="range" bind:value={priceMax} min="0" max="5000" step="50" />
            <p>{priceMax}</p>
        </div>
    </label>
    <label>
        <div class="flex-container">
            <p class="prop-name">Min Storage (GB):</p>
        </div>
        <div class="flex-container">
            <input type="range" bind:value={storageMin} min="0" max="2000" />
            <p>{storageMin}</p>
        </div>
    </label>
    <label>
        <div class="flex-container">
            <p class="prop-name">Max Storage (GB):</p>
        </div>
        <div class="flex-container">
            <input type="range" bind:value={storageMax} min="0" max="2000" />
            <p>{storageMax}</p>
        </div>
    </label>
    <label>
        <div class="flex-container">
            <input type="checkbox" bind:checked={hasWifi} />
            <p>WiFi</p>
        </div>
    </label>
    <label>
        <div class="flex-container">
            <input type="checkbox" bind:checked={has4g} />
            <p>4G</p>
        </div>
    </label>
    <button on:click={() => performSearch({ name, brand, minRAM, maxRAM, os, priceMin, priceMax, storageMin, storageMax, hasWifi, has4g })}>Search</button>
</div>

  <style>
.input {
    margin-left: auto;
    margin-right: auto;
    background-color: #f0f0f0;
    text-align: center;
    padding: 10px;
}

.flex-container {
    display: flex;
    justify-content: center;
}

.block-container{
    display: block;
}

input[type="range"] {
    flex-grow: 1;
}

input[type="text"]{
    width: 100%;
}

p {
    margin-left: 10px;
    padding-bottom: 10px;
    font-weight: bold;
    margin-top: 0px;
    margin-bottom: 0px;
}

.prop-name {
    font-size: large;
    margin-right: 10px;
}
</style>
