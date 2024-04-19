<script>
    let passage = 'This is my first time trying this.';
    let currInput = "";
    function handleInput(event){
        currInput = event.target.value;
    }
</script>

<div>
    <p>
        {#each passage.split('') as char, index}
            <span class={currInput.length > index && currInput[index] === char ? 'correct' : 'incorrect'}>{char}</span>
        {/each}
    </p>
</div>
<input type="text" bind:value={currInput} on:input={handleInput}/>

<style>
    .correct{
        color: green;
    }
    .incorrect{
        color:red;
    }
</style>