<svelte:head>
	<title>Test</title>
	<meta name="test" content="test to add new pages" />
</svelte:head>

<div class="text-column">
	<h1>Test</h1>

	<p>
		This is a test page for Tor Odin Ekle to learn Svelte. For more projects check my <a href="https://github.com/TorOEkle">GitHub</a>. 
		This page is built with SvelteKit. 
	</p>

	<p>
		Tor Odin is an Economist with mechanical background from manufacturing and oil industry that has went into tech and want to learn more. 
		Tools that I focus to learn more about now is Python, Streamlit, SQL and Svelte. 
	</p>
</div>
<script lang="ts">
	import { user } from "./store.js";
	function onSubmit(e) {
	  const formData = new FormData(e.target);
  
	  const data = {};
	  for (let field of formData) {
		const [key, value] = field;
		data[key] = value;
	  }
	  console.log(data)
	}
  </script>

<h1>Design Circle</h1>
<form class="content">
  <label>CX</label>
  <input type="text" bind:value={$user.cx} />
  <label>CY</label>
  <input type="text" bind:value={$user.cy} />
  <label>Radius</label>
  <input type="text" bind:value={$user.radius} />
  <label>Stroke[HEX]</label>
  <input type="text" bind:value={$user.stroke} />
  <label>Fill[HEX]</label>
  <input type="text" bind:value={$user.fill} />
</form>
 
 <style>
  .content {
    display: grid;
    grid-template-columns: 20% 80%;
    grid-column-gap: 10px;
  }
 </style>

<svg viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
	<circle cx={$user.cx} cy={$user.cy} r={$user.radius} stroke = {$user.stroke} fill = {$user.fill} />
  </svg>