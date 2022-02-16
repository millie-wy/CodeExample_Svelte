<script>
    import { fade, fly } from 'svelte/transition';
</script>

<div class="container" in:fly={{ y: 200, duration: 1000 }}>
    <div class="code">
        <img src="/images/arrow.png" alt="arrow">
        <h2>This navbar is the example!</h2>
    </div>

    <!-- Code example output -->
    <div class="output">
        {`<script>`}<br/>
        <span class="span-ml">{`import { createEventDispatcher } from "svelte";`}<br/></span>
        <span class="span-ml">{`const dispatch = createEventDispatcher();`}<br/><br/></span>
        <span class="span-ml">{`let menuItems = ['Component Structure', 'Binding: Text/Group Inputs', 'Props', 'Slots', 'Each Blocks'];`}<br/></span>
        <span class="span-ml">{`let activeItem = menuItems[0];`}<br/></span>
        {`</script>`}<br/><br/>
        {`<ul>`}<br/>
	    <span class="span-ml">{`{#each menuItems as item}`}<br/></span>
        <span class="span-ml"><span class="span-ml">{`<li on:click={() => dispatch('tabChange', item)}>`}<br/></span></span>
        <span class="span-ml"><span class="span-ml"><span class="span-ml">{`<div class:active={item === activeItem}>{item}</div>`}<br/></span></span></span>
        <span class="span-ml"><span class="span-ml">{`</li>`}<br/></span></span>
        <span class="span-ml">{`{/each}`}<br/></span>
        {`</ul>`}<br/><br/>
        {`<style>`}<br/>
        <span class="span-ml">{`ul { `}<br/></span>
        <span class="span-ml"><span class="span-ml">{`display: flex;`}<br/></span></span>
        <span class="span-ml"><span class="span-ml">{`flex-direction: row;`}<br/></span></span>
        <span class="span-ml"><span class="span-ml">{`list-style: none;`}<br/></span></span>
        <span class="span-ml"><span class="span-ml">{`justify-content: space-around;`}<br/></span></span>
        <span class="span-ml"><span class="span-ml">{`padding: 1rem;`}<br/></span></span>
        <span class="span-ml"><span class="span-ml">{`margin: 0;`}<br/></span></span>
        <span class="span-ml">{`}`}<br/><br/></span>
        <span class="span-ml">{`li { `}<br/></span>
        <span class="span-ml"><span class="span-ml">{`cursor: pointer;`}<br/></span></span>
        <span class="span-ml">{`}`}<br/><br/></span>
        <span class="span-ml">{`.active {`}<br/></span>
        <span class="span-ml"><span class="span-ml">{`color: rgb(192, 139, 83);`}<br/></span></span>
        <span class="span-ml"><span class="span-ml">{`border-bottom: 2px solid rgb(192, 139, 83);`}<br/></span></span>
        <span class="span-ml"><span class="span-ml">{`padding-bottom: 8px;`}<br/></span></span>
        <span class="span-ml">{`}`}<br/></span>
        {`</style>`}<br/>     
    </div>
    <!-- End of code example output -->

</div>

<style>
    img {
        margin-left: 10rem;
        height: 200px;
    }
</style>