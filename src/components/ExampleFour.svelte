<script>
    import ExampleFour2 from './ExampleFour2.svelte'; 
</script>

<div class="container">
    <div class="code">
        <ExampleFour2 let:isHovering={active}>
            <div class="box" class:active>  <!--class directive (shorthand)-->
                {#if active}
                    <h2>Hello there!! 😋</h2>
                {:else}
                    <h2>Hover over me! 👋</h2>
                {/if}
            </div>
        </ExampleFour2>
    </div>
    
    <div class="output">
        {`<-------- PARENT component -------->`}<br><br>
        {`<script>`}<br>
        <span class="span-ml">{`import ExampleFour2 from './ExampleFour2.svelte';`}</span><br>
        {`</script>`}<br><br>

        {`<ExampleFour2 let:isHovering={active}>`}<br>
        <span class="span-ml">{`<div class="box" class:active>`}</span><br>  
        <span class="span-ml"><span class="span-ml">{`{#if active}`}</span></span><br>
        <span class="span-ml"><span class="span-ml"><span class="span-ml">{`<h2>Hello there!! 😋</h2>`}</span></span></span><br>
        <span class="span-ml"><span class="span-ml">{`{:else}`}</span></span><br>
        <span class="span-ml"><span class="span-ml"><span class="span-ml">{`<h2>Hover over me! 👋</h2>`}</span></span></span><br>
        <span class="span-ml"><span class="span-ml">{`{/if}`}</span></span><br>
        <span class="span-ml">{`</div>`}</span><br>  
        {`</ExampleFour2>`}<br><br>

        {`<-------- CHILD component -------->`}<br><br>
        {`<script>`}<br>
        <span class="span-ml">{`let isHovering;`}<br><br></span>
        <span class="span-ml">{`const pointTarget = () => { isHovering = true };`}<br></span>
        <span class="span-ml">{`const leaveTarget = () => { isHovering = false };`}<br></span>
        {`</script>`}<br><br>
        {`<div on:mouseenter="{pointTarget}" on:mouseleave="{leaveTarget}">`}<br>
        <span class="span-ml">{`<slot {isHovering}></slot>`}<br></span>
        {`</div>`}<br><br>
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