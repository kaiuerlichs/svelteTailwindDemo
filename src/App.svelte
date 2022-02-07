<script>
	import ModelView from "./components/ModelView.svelte";
</script>

<div class="h-screen flex justify-center items-center">
	<ModelView on:closeModelView={() => {transitionTo("main")}}/>
</div>

<style global lang="postcss">
	@tailwind base;
	@tailwind components;
	@tailwind utilities;
</style>
