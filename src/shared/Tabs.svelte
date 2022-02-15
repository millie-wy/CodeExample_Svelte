<script>
    import { createEventDispatcher } from "svelte";
    const dispatch = createEventDispatcher();

    export let menuItems;
    export let activeItem;

</script>

<ul >
    {#each menuItems as item}
        <li on:click={() => dispatch('tabChange', item)}>
            <div class:active={item === activeItem}>{item}</div>
        </li>
    {/each}
</ul>

<style>
    ul { 
        display: flex;
        flex-direction: row;
        list-style: none;
        justify-content: space-around;
        padding: 1rem;
        margin: 0;
    }

    li {
        cursor: pointer;
    }

    .active {
        color: rgb(192, 139, 83);
        border-bottom:  2px solid  rgb(192, 139, 83);
        padding-bottom: 8px;
    }
</style>