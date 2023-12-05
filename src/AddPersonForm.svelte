<script>
let name;
let favoritecolor;
let age;
// let java = false;
// let python = false;
// let php = false;

let skills = [];


const handleSubmit = ()=>{
  console.log(name, favoritecolor,age,skills);
}
</script>

<form  on:submit|preventDefault={handleSubmit}>
	<input type="text" placeholder="name" bind:value={name}>
	<!-- <input type="text" placeholder="favorite color" bind:value={favoritecolor}> -->
  <input type="number" placeholder="age" bind:value={age}>
  <!-- svelte-ignore a11y-label-has-associated-control -->
  <label> Programming Languages:</label>
  <input type="checkbox" bind:group={skills} value="java">Java<br> 
  <input type="checkbox"  bind:group={skills} value="python">Python<br>
  <input type="checkbox"  bind:group={skills} value="php">PHP<br>
  <!-- svelte-ignore a11y-label-has-associated-control -->
  <label>favoritecolor</label>
    <select bind:value={favoritecolor}>
    <option value="black">Balck</option>
    <option value="red">Red</option>
    <option value="blue">Blue</option>
    <option value="white">White</option>
    </select>
	<button>Add Person</button>
</form>

<style>

</style>