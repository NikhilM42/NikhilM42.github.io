<script lang="ts">
  import { navbarmenu, maincolor } from "../constants";
	import Button from "./Button.svelte";

	export let navtop = false;
	export let navSelection = "Home";

	function btnClick(val) {
		navSelection = val;
	}
</script>

<nav class="right {navtop ? "top":""}" style="--theme-color: {maincolor}">
  <ul>
    {#each navbarmenu as item}
			<li>
				<Button buttontext={item} largeMode={!navtop} on:click={() => btnClick({item})}/>
			</li>
		{/each}
  </ul>
</nav>

<style>
  .right {
		background-color: var(--theme-color);
		width: 100%;
		height: 100%;
		display: flex;
    flex-direction: column;
    align-content: flex-start;
    justify-content: center;
    align-items: flex-start;
	}
	.top ul {
		flex-direction: row;
		padding-inline-start: 0%;
	}
	ul {
		width: 100%;
    padding-inline-start: 2.9vw;
		display: flex;
		flex-direction: column;
		transition: 2s;
	}
	li {
		list-style-type: none;
		width: 100%;
	}
</style>