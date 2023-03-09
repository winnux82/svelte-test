<script>
	import { createEventDispatcher } from 'svelte';
	export let bar = 'optional default initial value';
	// export let baz = undefined;
	let title = 'Welcome to my playlist!';
	let name = 'message de sam';

	let nb1 = 10;
	let nb2 = 10;
	let result = 0;
	function calculate() {
		result = nb1 * nb2;
	}
	// setInterval(() => {
	// 	console.log('name', name);
	// }, 2000);

	let count = 0;

	function handleClick() {
		count = count + 1;
	}

	let user = {
		firstname: 'Ada',
		lastname: 'Lovelace'
	};
</script>

<h1>{title}</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
{bar}
<!-- {baz} -->

<button on:click={handleClick}>
	Clicked {count}
	{count === 1 ? 'time' : 'times'}
</button>
<h2>{count}</h2>
{#if count % 2 === 0}
	<p>Count {count} est divisible par 2</p>
{/if}

<div>
	1 x {count} = {1 * count}<br />
	2 x {count} = {2 * count}<br />
	3 x {count} = {3 * count}<br />
	4 x {count} = {4 * count}<br />
	5 x {count} = {5 * count}<br />
	6 x {count} = {6 * count}<br />
	7 x {count} = {7 * count}<br />
	8 x {count} = {8 * count}<br />
	9 x {count} = {9 * count}<br />
	10 x {count} = {10 * count}<br />
</div>

<input bind:value={name} />
<br />
<h3>Via variable</h3>
<input bind:value={nb1} />*<input bind:value={nb2} />
{nb1 * nb2}

<h3>Via on:keyup</h3>
<input bind:value={nb1} on:keyup={calculate} />*<input bind:value={nb2} on:keyup={calculate} />
Résultat: {result}

{@debug user}

<h1>Hello {user.firstname}!</h1>
