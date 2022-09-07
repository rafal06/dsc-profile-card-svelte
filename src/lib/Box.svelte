<script>
    import { scale } from 'svelte/transition';


</script>

<div class="card" in:scale out:scale>
    <h2>Example text</h2>
</div>

<style>
    .card {
        background-color: #242424;

        position:  absolute;
        top:       50vh;
        left:      50vw;
        transform: translate(-50%, -50%);

        width:     700px;
        height:    400px;
        z-index:   2137;
        padding: 2em;
        text-align: center;
    }
</style>
