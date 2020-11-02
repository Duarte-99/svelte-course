<script>
    import {onMount} from 'svelte';

    let photos = [];

    onMount(async () => {
        console.log('onMount')
        const response = await fetch('https://jsonplaceholder.typicode.com/photos?_limit=20');
        photos = await response.json();
    });
</script>

<style>
    .Pothos {
        display: grid;
        grid-template-columns: repeat(5, 1fr);
        gap: 3rem;
        padding: 2.5rem;
    }
</style>

<div class="Pothos">
    {#each photos as photo}
        <figure>
            <img src={photos.thumbnailURL} alt={photo.title}>
            <figcaption>{photo.title}</figcaption>
        </figure>
        {:else}
            <p>Loading...</p>

    {/each}
</div>

