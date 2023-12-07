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

let isOn = {
    name: false,
    brand: false,
    minRAM: false,
    maxRAM: false,
    os: false,
    priceMin: false,
    priceMax: false,
    storageMin: false,
    storageMax: false,
    hasWifi: false,
    has4g: false,
}
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
        <div class="flex-container">
            <p class="prop-name">Min Price:</p>
            <input type="checkbox" bind:checked={isOn.priceMin}>
        </div>
        <div class="flex-container">
            <input type="range" bind:value={priceMin} min="0" max="5000" step="1" />
            <p>{priceMin}</p>
        </div>
    </label>
    <label>
        <div class="flex-container">
            <p class="prop-name">Max Price:</p>
            <input type="checkbox" bind:checked={isOn.priceMax}>
        </div>
        <div class="flex-container">
            <input type="range" bind:value={priceMax} min="0" max="5000" step="50" />
            <p>{priceMax}</p>
        </div>
    </label>
    <label>
        <div class="flex-container">
            <p class="prop-name">Min Storage (GB):</p>
            <input type="checkbox" bind:checked={isOn.storageMin}>
        </div>
        <div class="flex-container">
            <input type="range" bind:value={storageMin} min="0" max="2000" />
            <p>{storageMin}</p>
        </div>
    </label>
    <label>
        <div class="flex-container">
            <p class="prop-name">Max Storage (GB):</p>
            <input type="checkbox" bind:checked={isOn.storageMax}>
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
}

.flex-container {
    display: flex;
    justify-content: center;
}

input[type="range"] {
    flex-grow: 1;
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
