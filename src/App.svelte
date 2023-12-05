<script>
	import AddPersonForm from './AddPersonForm.svelte'
	import Model from  './Model.svelte'
	 let name ='Harish'
	 let showModel= false;

	 const toggleModel = () =>{
		showModel = !showModel;
	 }
	 let isPromo =false;
	 //let age=26
	 //
	 let firstName = 'Kummara'
	 let lastName = 'Harish'
	 let beltcolor ='black'

	 let people = [
		{name: 'harish', beltcolor: 'pink', age: 25, id:1},
		{name: 'rekha', beltcolor: 'red', age: 24, id:2},
		{name: 'muni', beltcolor: 'yellow', age: 35, id:3},
		{name: 'divya', beltcolor: 'green', age: 29, id:4}
	 ]

	 $: fullName = `${firstName} ${lastName}`;
	  
	 const changeClr = ()=>{
		beltcolor='red';
	 };

	 const handleInput= (e)=>{
			beltcolor = e.target.value;
	 };
	 const deletePerson = (id)=>{
		//console.log(id);
		people = people.filter((person)=> person.id != id);
	 }

	 //if condition
	 let age =111;
	 

</script>
<Model {isPromo} {showModel} on:click={toggleModel}>


<!--<div slot="title">
	<h3>Add New Person Address</h3>
</div>-->
<AddPersonForm/>
</Model>


<!--if condition-->
<!--{#if age<10}
<p>your are kid</p>
{:else if age>10 && age<20}
<p>your are adult</p>
{:else if age>20 && age<70}
<p>your person</p>
{:else if age>70 && age<100 }
<p>your are old</p>
{:else}
<p>invaid age..</p>
{/if}-->

<main>
	
	
	<button on:click|once={toggleModel}>Open Model</button>
		{#each people as person(person.id) }
			<div>
				<h4>person name:{person.name}</h4>
				<p>{person.age}years old,beltclor is {person.beltcolor}</p>
				<button on:click={()=> deletePerson(person.id)}>Delete</button>
			</div>
			{:else}
				<p>There are no people to show here ....</p>
		{/each}
	
<!--<h1>Hello {name}!</h1>
	<p>Welcome to all</p>
	<p>My age is {age}</p>
	<p style="color: {beltcolor};" > {beltcolor} belt</p>
	<button on:click={changeClr}>Change Beltcolor</button>
	<input type="text" on:input={handleInput} value={beltcolor}>
	<input type="text" bind:value={beltcolor}>
	<h1>Hello All !</h1>
	<p>{fullName} {beltcolor} belt</p>
	<input type="text" bind:value={firstName}>
	<input type="text" bind:value={lastName}>
	<input type="text" bind:value={beltcolor}>-->
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
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