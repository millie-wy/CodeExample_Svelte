<script>
    export let answer;
    export let imgSrc;
    export let imgAlt;
</script>

<h2>My favorite food is {answer}. Here is a picture of it...</h2>
<img src={imgSrc} alt={imgAlt}>

<style>
    img {
        width: 10rem;
    }
</style>