<script>
    import Counter from "../../lib/components/counter.svelte";
    import DoubleCounter from "../../lib/components/double_counter.svelte";
    let contatore = 1;
    let contatore1 = 1;
</script>

<header>
    <h1>Counter page</h1>
</header>

<Counter bind:counter={contatore1}/>
<h3>Counter settato a {contatore1}</h3>

<DoubleCounter bind:counter={contatore}/>
<h3>Double Counter settato a {contatore}</h3>
