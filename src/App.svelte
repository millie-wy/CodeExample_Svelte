<script>
	import Header from './components/Header.svelte'
	import Footer from './components/Footer.svelte'
	import Ex1 from './components/Ex1.svelte'
	import Ex2 from './components/Ex2.svelte'
	import Ex3 from './components/Ex3-1.svelte'
	import Ex4 from './components/Ex4-1.svelte'
	import Ex5 from './components/Ex5.svelte'
	import Tabs from './shared/Tabs.svelte'

	// Menu
	let menuItems = ['Component Structure', 'Binding: Text/Group Inputs', 'Props', 'Slots', 'Each Blocks'];
    let activeItem = menuItems[0];

	const tabChange = (e) => {
		activeItem = e.detail;
	}
</script>

<Header />
<main>
	<Tabs {activeItem} {menuItems} on:tabChange={tabChange}/>
    {#if activeItem === menuItems[0]}
        <Ex1 />
	{:else if activeItem === menuItems[1]}
		<Ex2 />
	{:else if activeItem === menuItems[2]}
		<Ex3 />
	{:else if activeItem === menuItems[3]}
		<Ex4 />
	{:else if activeItem === menuItems[4]}
		<Ex5 />
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