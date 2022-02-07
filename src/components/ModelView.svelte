<script>
    import { createEventDispatcher } from 'svelte';
    import { fade } from 'svelte/transition';
    const dispatch = createEventDispatcher();

    export let config = "";
    config = config;

    function clickHandler(){
        dispatch("closeModelView")
    }
</script>

<div class="rounded-[30px] h-[95%] w-[95%] overflow-hidden relative shadow-md bg-slate-800">
    <iframe
        src="./scene.html"
        title="AR Scene"
        frameborder="0"
        class="absolute h-full w-full"
    />
    <div class="absolute top-10 right-10 bg-orange-50 rounded-[20px] p-5 shadow-lg" on:click={clickHandler}>
        <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-5 w-5"
            viewBox="0 0 20 20"
            fill="currentColor"
        >
            <path
                fill-rule="evenodd"
                d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
                clip-rule="evenodd"
            />
        </svg>
    </div>
</div>
