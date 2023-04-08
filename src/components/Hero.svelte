<script lang="ts">
    import { onMount } from 'svelte';

    onMount(() => {
        const left = document.getElementById("left-box");

        const handleOnMove = (e: { clientX: number; }) => {
            const x = e.clientX / window.innerWidth * 100;

            if (left)
                left.style.width = x + "%";
        }

        document.onmousemove = e => handleOnMove(e);
    });

</script>

<main class="h-screen overflow-hidden relative">
    <div class="h-screen w-full overflow-hidden absolute z-20
    bg-stone-50 text-stone-950" id="left-box">
        <div class="w-screen h-screen flex flex-col items-center justify-center">
            <h1 class="font-bold text-7xl my-6">
                The <span class="code bg-clip-text text-transparent bg-gradient-to-r from-sky-500 to-purple-400 ">
                    sceptix</span> club
            </h1>
            <h3 class="text-3xl font-mono">
                Liberate The Mind
            </h3>
        </div>
    </div>
    <div class="h-screen w-full overflow-hidden absolute z-10
    bg-stone-950 text-stone-50" id="right-box">
        <div class="w-full h-screen flex flex-col items-center justify-center">
            <h1 class="font-bold text-7xl my-6">
                The <span class="code bg-clip-text text-transparent bg-gradient-to-r from-green-400 to-sky-400">
                    freedom</span> club
            </h1>
            <h3 class="text-3xl font-mono">
                Unchain Your Will
            </h3>
        </div>
    </div>
</main>

<style lang="postcss">
    .code {
        font-weight: 700;
    }
</style>
