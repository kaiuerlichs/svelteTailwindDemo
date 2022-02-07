<script>
	import statefulSwap from "./statefulSwap"
	import ModelView from "./components/ModelView.svelte";
	import {fade} from "svelte/transition"
	const {onOutro, transitionTo, state} = statefulSwap("main")
</script>

<div class="h-screen flex justify-center items-center">

	{#if $state == "main"}
		<button class="p-3 bg-slate-800 text-white font-mono shadow-md" on:click={() => transitionTo("model")} on:outroend={onOutro} transition:fade>
			Launch Model Viewer
		</button>
	{:else if $state == "model"}
		<div class="h-[95%] w-[95%]" on:outroend={onOutro} transition:fade>
			<ModelView on:closeModelView={() => transitionTo("main")}/>
		</div>
	{/if}
</div>

<style global lang="postcss">
	@tailwind base;
	@tailwind components;
	@tailwind utilities;
</style>
