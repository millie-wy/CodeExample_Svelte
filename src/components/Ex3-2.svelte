<script>
    import { spring } from 'svelte/motion';
    export let answer;
    export let imgSrc;
    export let imgAlt;

    const width = spring(100, {
        stiffness: 0.01,
        damping: 0.01
    });
    setInterval(() => { width.set(200) }, 100)
    setInterval(() => { width.set(100) }, 250)
</script>

<h2>My favorite food is {answer}. Here is a picture of it...</h2>
<img src={imgSrc} alt={imgAlt} width={$width}>

<style>
</style>