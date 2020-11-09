<script>
    import { createEvenDispatcher } from 'svelte';

    let dispatch = createEvenDispatcher();

    let name;
    let beltColour;
    let age;
    let fighting = false;
    let sneaking = false;
    let running = false;

    const handleSubmit = () => {
        console.log(name, beltColour, age, fighting, sneaking, running);   
        const person = {
            name,
            beltColour,
            age,
            skills,
            id: Math.random()
        }
        dispatch('addPerson', person);
    };
</script>

<form on:submit|preventDefault={handleSubmit}>
		<input type="text" placeholder="name" bind:value={name}>
        <input type="text" placeholder="belt colour" bind:value={beltColour}>
        <input type="number" bind:value={age}>
        <label>Skills:</label>
        <input type="checkbox" bind:checked={fighting}>fighting<br>
        <input type="checkbox" bind:checked={sneaking}>sneaking<br>
        <input type="checkbox" bind:checked={running}>running<br>
        <label>Belt colour</label>
        <select bind:value={beltColour}>
            <option value="black">black</option>
            <option value="orange">orange</option>
            <option value="brown">brown</option>
            <option value="white">white</option>
        </select>
		<button>Add Person</button>
</form>

<style>

</style>