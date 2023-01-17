<script>
    let count = 0;
    $: doubled = count * 2;
</script>

<h1>Grade Calculator</h1>
<button on:click={() => count += 1}>
    Clicked {count} {count === 1 ? 'time' : 'times'}
    (Double is {doubled})
</button>




