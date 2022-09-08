<script>
    import { fade } from 'svelte/transition'
	import Box from './lib/Box.svelte';

	let boxShown = false;
    // $: console.log(boxShown);
	function toggleBox() {
		boxShown = !boxShown;
	}
</script>

<main>
    <div class="card-container">
        {#if boxShown}
            <div
                class="box"
                on:click={toggleBox}
                in:fade
                out:fade
            >
            </div>
            <Box/>
        {/if}
        <button on:click={toggleBox}>Show</button>
    </div>
</main>

<style>
    .card-container {
        height: min-content;
    }

    main {
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .box {
        position: absolute;
        left: 0;
        top: 0;
        width: 100vw;
        height: 100vh;
        background-color: #00000061;
        /* transition: 1000ms; */
    }
</style>
