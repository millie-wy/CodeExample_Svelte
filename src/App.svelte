<script>
	import Header from './components/Header.svelte'
	import Footer from './components/Footer.svelte'
	import ExampleOne from './components/ExampleOne.svelte'
	import ExampleTwo from './components/ExampleTwo.svelte'
	import ExampleThree from './components/ExampleThree.svelte'
	import ExampleFour from './components/ExampleFour.svelte'
	import ExampleFive from './components/ExampleFive.svelte'
	import Tabs from './shared/Tabs.svelte'

	// Menu
	let menuItems = ['Component Structure', 'Binding: Text/Group Inputs', 'Props', 'Slots', 'Each Blocks'];
    let activeItem = menuItems[4];

	const tabChange = (e) => {
		activeItem = e.detail;
	}
</script>

<Header />
<main>
	<Tabs {activeItem} {menuItems} on:tabChange={tabChange} />
    {#if activeItem === menuItems[0]}
        <ExampleOne />
	{:else if activeItem === menuItems[1]}
		<ExampleTwo />
	{:else if activeItem === menuItems[2]}
		<ExampleThree />
	{:else if activeItem === menuItems[3]}
		<ExampleFour />
	{:else if activeItem === menuItems[4]}
		<ExampleFive />
	{/if}
</main>
<Footer />

<style>
	main {
        background: rgb(252, 249, 245);
		min-height: calc(100vh - 8.5rem);
		padding-bottom: 2.5rem;
	}
</style>