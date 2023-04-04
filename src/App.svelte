<script lang="ts">
    import Game from "./Game.svelte";
</script>

<main>
    <h1>Minesweeper</h1>
    <p>
        The <span class="a1v0">a1v0</span> implementation we've all been waiting
        for!
    </p>
    <Game />
</main>

<style>
    main {
        text-align: center;
        padding: 1em;
        max-width: 240px;
        margin: 0 auto;
    }

    span.a1v0 {
        font-family: Consolas, "Courier New", Courier, monospace;
        font-weight: bold;
    }

    h1 {
        color: #ff3e00;
        text-transform: uppercase;
        font-size: 4em;
        font-weight: 100;
    }

    @media (min-width: 640px) {
        main {
            max-width: none;
        }
    }
</style>
