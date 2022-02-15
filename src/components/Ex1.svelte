<script>
    import { fade, fly } from 'svelte/transition';
    let name = 'Millie';
</script>

<div class="container" in:fly={{ y: 200, duration: 1000 }}>
    <div class="code">
        <h2>My name is {name}!</h2>
    </div>
    <div class="output">
        {`<script>`}<br/>
	    <span class="span-ml">{`let name = 'Millie';`}<br/></span>
        {`</script>`}<br/><br/>
        {`<h2>My name is {name}!</h2>`}<br/><br/>
        {`<style>`}<br/>
        <span class="span-ml">{`h2 { color: rgb(122, 95, 60); }`}<br/></span>
        {`</style>`}<br/>     
    </div>
</div>


<style>
    h2 {
        color: rgb(122, 95, 60);
    }
</style>