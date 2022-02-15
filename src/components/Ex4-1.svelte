<script>
    import Ex4child from './Ex4-2.svelte'; 
    import { fade, fly } from 'svelte/transition';

</script>

<div class="container" in:fly={{ y: 200, duration: 1000 }}>
    <div class="code">
        <Ex4child let:isHovering={active}>
            <div class="box" class:active>  <!--class directive (shorthand)-->
                {#if active}
                    <h2 in:fade>Hello there!! 😋</h2>
                {:else}
                    <h2 in:fade>Hover over me! 👋</h2>
                {/if}
            </div>
        </Ex4child>
    </div>
    
    <div class="output">
        {`<-------- PARENT component -------->`}<br/><br/>
        {`<script>`}<br/>
        <span class="span-ml">{`import Ex4child from './Ex4-2.svelte';`}</span><br/>
        {`</script>`}<br/><br/>

        {`<Ex4child let:isHovering={active}>`}<br/>
        <span class="span-ml">{`<div class="box" class:active>`}</span><br/>  
        <span class="span-ml"><span class="span-ml">{`{#if active}`}</span></span><br/>
        <span class="span-ml"><span class="span-ml"><span class="span-ml">{`<h2>Hello there!! 😋</h2>`}</span></span></span><br/>
        <span class="span-ml"><span class="span-ml">{`{:else}`}</span></span><br/>
        <span class="span-ml"><span class="span-ml"><span class="span-ml">{`<h2>Hover over me! 👋</h2>`}</span></span></span><br/>
        <span class="span-ml"><span class="span-ml">{`{/if}`}</span></span><br/>
        <span class="span-ml">{`</div>`}</span><br/>  
        {`</Ex4child>`}<br/><br/>
        {`<style>`}<br/>
        <span class="span-ml">{`.box {`}<br/></span>
        <span class="span-ml"><span class="span-ml">{`background: rgb(243, 236, 228);`}</span></span><br/>
        <span class="span-ml"><span class="span-ml">{`height: 5rem;`}</span></span><br/>
        <span class="span-ml"><span class="span-ml">{`display: flex;`}</span></span><br/>
        <span class="span-ml"><span class="span-ml">{`place-content: center;`}</span></span><br/>
        <span class="span-ml"><span class="span-ml">{`place-items: center;`}</span></span><br/>
        <span class="span-ml">{`}`}<br/><br/></span>
        <span class="span-ml">{`.active {`}<br/></span>
        <span class="span-ml"><span class="span-ml">{`background: rgb(235, 181, 119);`}</span></span><br/>
        <span class="span-ml"><span class="span-ml">{`color: whitesmoke;`}</span><br/>
        <span class="span-ml">{`}`}<br/></span>
        {`</style>`}<br/><br/>

        {`<-------- CHILD component -------->`}<br/><br/>
        {`<script>`}<br/>
        <span class="span-ml">{`let isHovering;`}<br/><br/></span>
        <span class="span-ml">{`const pointTarget = () => { isHovering = true };`}<br/></span>
        <span class="span-ml">{`const leaveTarget = () => { isHovering = false };`}<br/></span>
        {`</script>`}<br/><br/>
        {`<div on:mouseenter="{pointTarget}" on:mouseleave="{leaveTarget}">`}<br/>
        <span class="span-ml">{`<slot {isHovering}></slot>`}<br/></span>
        {`</div>`}<br/><br/>
    </div>
</div>



<style>
    .box {
        background: rgb(243, 236, 228);
        height: 5rem;
        display: flex;
        place-content: center;
        place-items: center;
    }

    .active {
        background: rgb(235, 181, 119);
        color: whitesmoke;
    }
</style>