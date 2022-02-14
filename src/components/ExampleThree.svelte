<script>
    import ExampleThree2 from './ExampleThree2.svelte'; // passing data down to child

    let imgSrc = '/images/burger.svg';
    let imgAlt = 'hamburger';
</script>

<div class="container">
    <div class="code">
        <ExampleThree2 answer={'burgers'} {imgSrc} {imgAlt} />
    </div>
    
    <div class="output">
        {`<-------- PARENT component -------->`}<br><br>
        {`<script>`}<br>
        <span class="span-ml">{`import ExampleThree2 from './ExampleThree2.svelte';`}</span><br><br>
        <span class="span-ml">{`let imgSrc = '/images/burger.svg';`}</span><br>
        <span class="span-ml">{`let imgAlt = 'hamburger';`}</span><br>
        {`</script>`}<br><br>

        {`<ExampleThree2 answer={'burgers'} {imgSrc} {imgAlt} />`}<br><br>

        {`<-------- CHILD component -------->`}<br><br>
        {`<script>`}<br>
        <span class="span-ml">{`export let answer;`}<br></span>
        <span class="span-ml">{`export let imgSrc;`}<br></span>
        <span class="span-ml">{`export let imgAlt;`}<br></span>
        {`</script>`}<br><br>
        {`<h2>My favorite food is {answer}. Here is a picture of it...</h2>`}<br>
        {`<img src={imgSrc} alt={imgAlt}>`}<br><br>
        {`<style>`}<br>
        <span class="span-ml">{`img { width: 10rem; }`}<br></span>
        {`</style>`}<br><br>
    </div>
</div>
