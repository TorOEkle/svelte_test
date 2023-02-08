<svelte:head>
	<title>Circle design</title>
	<meta name="test" content="test to add new pages" />
</svelte:head>


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
    grid-template-columns: 20% 22%;
    grid-column-gap: 5px;
  }
 </style>

<svg viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
	<circle cx={$user.cx} cy={$user.cy} r={$user.radius} stroke = {$user.stroke} fill = {$user.fill} />
  </svg>