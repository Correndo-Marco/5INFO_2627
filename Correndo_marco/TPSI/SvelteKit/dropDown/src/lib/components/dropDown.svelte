<script>
    import { DropItem } from "./dropItem.svelte";
    export let nome;
    export let valori;
    let stato = false;
</script>

<h1>{nome}</h1>

<ul>
    {#each valori.split(",") as val}
        <li class:stato><DropItem valore={val} /></li>
    {/each}
</ul>

<style>
    .stato{
        visibility: hidden;
    }
</style>
