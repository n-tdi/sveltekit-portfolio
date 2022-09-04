<script>
    import HeaderButtons from "$lib/components/HeaderButtons.svelte";
    import { fade, slide, scale } from "svelte/transition";
    import { flip } from 'svelte/animate';
    import HomePage from "$lib/components/Home/HomePage.svelte";
    import ProjectPage from "$lib/components/Projects/ProjectPage.svelte";

    const Pages = {
        Home: 0,
        Timeline: 1
    }

    let page = Pages.Home;

    const homeClick = () => {
        page = Pages.Home;
    }
    const projectClick = () => {
        page = Pages.Timeline;
    }
</script>

<div class="left--container" >
    <div class="left--container__top">
        <div class="left--container__button">
            <HeaderButtons homeClick={homeClick} projectClick={projectClick} />
        </div>
    </div>
    <div class="left--container__bottom" > 
        {#if page == Pages.Home}
            <div class="container--home" transition:slide|local >
                <HomePage />
            </div>
        {/if}
        {#if page == Pages.Timeline}
            <div class="container--timeline" transition:slide|local >
                <ProjectPage />
            </div>
        {/if}
    </div>
</div>

<style lang=scss>
    .left--container {
        width: 70%;
        height: 90%;
        .left--container__top {
            display: flex;
            justify-content: center;
        }
    }

    @media only screen and (max-width: 850px) {
        .left--container {
            width: 90%;
        }
    }
    @media only screen and (max-width: 575px) {
        .left--container {
            width: 96%;
        }
    }
</style>