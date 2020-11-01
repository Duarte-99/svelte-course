<script>
    let someText = `Backend Developer at HardSoftDay`
    let count = 0;

    let styles = {darkMode: false}
    let stylesLight = {lightMode: false}

    function handleClick() {
        count += 1
    }

    function toggle() {
        styles.darkMode = !styles.darkMode;
        stylesLight.lightMode = !stylesLight.lightMode;

        window.document.body.classList.toggle("dark-mode")
        window.document.body.classList.toggle("light-mode")
    }

</script>

<style>

    p {
        color: var(--theme-color);
    }

</style>

<div class="About">


    {#if !styles.darkMode}
        <p>
            {someText}
        </p>
        <p>
            <span>Light Mode</span>
        </p>
    {:else}

        <button on:click={toggle}>LightMode</button>
        <p>
            <span>Dark Mode</span>
        </p>

    {/if}



        <button on:click={handleClick}>Click {count === 0 ? '' : count}</button>
        <button on:click={toggle}>DarkMode</button>


 </div>
