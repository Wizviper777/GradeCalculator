<script>
    let values = [{grade: 0, weight: 0}];
    function addSection() {
        values = [...values, {grade: 0, weight: 0}];
    }
    function removeSection() {
        values = values.slice(0, -1);
    }
    $: total = values.reduce((acc, {grade, weight}) => acc + (weight * grade / 100), 0);
</script>

<div id='container'>
<h1>Grade Calculator</h1>
{#each values as value, i}
    <div class='inputBox'>
        <label for="grade">Grade(%)</label>
        <input type="number" name="grade" bind:value={value.grade} />
        <label for="weight">Weight(%)</label>
        <input type="number" name="weight" bind:value={value.weight} />
    </div>
{/each}
<h2>Total: {total}%</h2>
<button on:click={addSection}>Add Section</button>
<button on:click={removeSection}>Remove Section</button>
</div>

<style>
    * {
        font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
    }
    #container {
        display: flex;
        flex-direction: column;
        align-items: center;
        height: 100vh;
        width: 100vw;
    }

    .inputBox {
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        align-items: center;
        width: 40%;
        height: 5%;
    }

    button {
        width: 10%;
        height: 5%;
        margin: 0.25%;
        background-color: aquamarine;
        color: black;
    }
</style>





