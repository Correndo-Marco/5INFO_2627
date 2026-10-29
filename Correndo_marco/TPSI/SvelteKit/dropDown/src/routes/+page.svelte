<script>
    import DropDown from "../lib/components/dropDown.svelte";
    let valori = {
        "Regione" : ["Piemonte","Liguria","Lombardia"],
        "Stato" : ["Italia","Germania","Giappone"],
        "Citta" : ["Torino","Genova","Milano"]
    };
</script>

<h1>DROP DOWN TESTER</h1>

<div class="cont">
    {#each Object.keys(valori) as nome}
        <DropDown nome={nome} valori={valori[nome]} />
    {/each}
</div>

<style>
    .cont{
        align-items: center;
        width: 30%;
    }
</style>
