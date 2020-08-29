<script>

	import Header from './components/Header.svelte'
	import Footer from './components/Footer.svelte'
	import PollList from './components/PollList.svelte'
	import CreatePollForm from './components/CreatePollForm.svelte'
	import Tabs from './shared/Tabs.svelte'

	//tabs
	let items = ['Current Polls', 'Add New Poll']
	let activeItem = 'Current Polls'

	const tabChange = e => {
		activeItem = e.detail
	} 


	const onAdd = e => {
		activeItem = 'Current Polls'
	}

	

</script>

<Header/>
<main>
	<Tabs {activeItem} {items} on:tabChange={tabChange}/>
	{#if activeItem === 'Current Polls'}
		<PollList />
	{:else if activeItem === 'Add New Poll'}
		<CreatePollForm on:add={onAdd} />
	{/if}
		
</main>
<Footer/>
<style>
	main{
		max-width: 960p;
		margin: 40px;
	}
</style>