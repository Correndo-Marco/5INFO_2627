<script>
    import DropItem from "./dropItem.svelte";
    import { createEventDispatcher } from 'svelte';
    import { last } from "../js/store.js"

    const dispatch = createEventDispatcher();
    export let nome;
    export let valori;
    let stato = true;

    function emetti(valore){
        dispatch('DropDown',{
            nome: valore
        });
    }
    function manda(){
        stato = !stato
        emetti(nome)
    }
    function fun(){
        stato = !stato;
        if(!stato){
           $last = nome 
        }else if($last != nome){
            stato = true;
        }
        
    }

</script>

<div class="titolo">
    <h1 on:click={fun}>{nome}</h1>
</div>

<ul>
    {#each valori as val}
        <li class:stato>
            <DropItem valore={val} />
        </li>
    {/each}
</ul>

<style>
    .titolo{
        width: auto;    
    }
    h1 {
        background-color: red;
        border-radius: 10px;
        color: white;
    }
    .stato{
        visibility: hidden;
        height: 0px;
        margin: 0px;
    }
</style>
