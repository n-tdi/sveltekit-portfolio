<script>
    import { fade } from 'svelte/transition';
    import ProjectItem from '$lib/components/Projects/ProjectItem.svelte';

    let current = 'tazpvp'
</script>

<div class="container">
    <div class="projects">
        <div class="proj--left">
            <button 
            class="proj--select {current === 'tazpvp' ? 'proj--selected' : ''}"
            on:click={() => current = 'tazpvp'}
            >Tazpvp</button>
            <button 
            class="proj--select {current === 'ldsync' ? 'proj--selected' : ''}"
            on:click={() => current = 'ldsync'}
            >LDSync</button>
            <button 
                class="proj--select {current === 'fache' ? 'proj--selected' : ''}"
                on:click={() => current = 'fache'}
            >Fache</button>
            <button 
                class="proj--select {current === 'spindom' ? 'proj--selected' : ''}"
                on:click={() => current = 'spindom'}
            >Spindom</button>
            <button 
                class="proj--select {current === 'mathc' ? 'proj--selected' : ''}"
                on:click={() => current = 'mathc'}    
            >MathC</button>
            <button 
                class="proj--select {current === 'sbsniper' ? 'proj--selected' : ''}"
                on:click={() => current = 'sbsniper'}
            >Sniper</button>
        </div>
        <div class="proj--right">
            {#if current === 'tazpvp'}
                <div class="proj--container" in:fade={{duration: 100}}>
                    <ProjectItem title={"TAZPVP"} languages={"Java, Spigot, PostgresSQL"} body={
                    "Tazpvp is a Minecraft server that has had thousands of players online simultaneously. Tazpvp has unique pvp progression and game mechanics, making it stand out from other servers. *I've worked on Tazpvp for four months and contributed more than 20,000 lines of code."
                    } githubURL={"https://github.com/tazpvp/tazpvp"}/>
                </div>
            {/if}
            {#if current === 'ldsync'}
                <div class="proj--container" in:fade={{duration: 100}}>
                    <ProjectItem title={"LDSYNC"} languages={"Java, Spigot, JDA"} body={
                    "LDSync is the goto plugin for syncing Minecraft to Discord! LDSync provides the ability to sync Luckperms/Pex groups that hook into vault to discord roles. Featuring a rich config, LDSync is the only plugin of its kind. *LDSync was fully coded by me and is publicly available on SpigotMC aswell"
                    } githubURL={"https://github.com/professional-tdi/LDSync"}/>
                </div>
            {/if}
            {#if current === 'fache'}
                <div class="proj--container" in:fade={{duration: 100}}>
                    <ProjectItem title={"FACHE"} languages={"SvelteKit, Firebase"} body={
                    "Fache is my favorite fullstack web application. Using firebase to manage signing up, logging in, and per-user data, this web app is a great demonstration of my ability of functionality. (Rather than prettiness 😜) *Try it out for yourself."
                    } githubURL={"https://file-portal-hi6k2jyrq-professional-tdi.vercel.app/"}/>
                </div>
            {/if}
            {#if current === 'spindom'}
                <div class="proj--container" in:fade={{duration: 100}}>
                    <ProjectItem title={"SPINDOM"} languages={"C#, Unity"} body={
                    "Spindom is a reaction time based game in which you try to align two objects together to continue making music. Spindom has loads of settings making it very user friendly. Spindom is run on the web using WebGL so no need to download anything! *Spindom is apart of my game studio, TDI GAMES, which contains other simple games made in unity."
                    } githubURL={"https://tdi-games.github.io/Hub/"}/>
                </div>
            {/if}
            {#if current === 'mathc'}
                <div class="proj--container" in:fade={{duration: 100}}>
                    <ProjectItem title={"MATHC"} languages={"Java, Spigot"} body={
                    "MathC or Math in Chat is a plugin that improves user activity by adding fun math questions, in chat! MathC is highly configurable making server owners have a smooth time using it. *MathC was my first offical SpigotMC resource that gained numerous downloads."
                    } githubURL={"https://github.com/professional-tdi/MathC"}/>
                </div>
            {/if}
            {#if current === 'sbsniper'}
                <div class="proj--container" in:fade={{duration: 100}}>
                    <ProjectItem title={"SNIPER"} languages={"Python, RESTful Api, Oracle Cloud"} body={
                    "(Skyblock) Sniper is a program designed for users to find cheap auctions on Hypixel Skyblock without having to search for ages, using the Hypixel API. *I made this project more accessible to majority of players who dont know how to set it up by adding a webhook feature. Everytime there is a good flip the bot will send all the information needed to the given webhook. *I host this service on my Oracle Cloud server in Montreal."
                    } githubURL={"https://github.com/professional-tdi/MathC"}/>
                </div>
            {/if}
        </div>
    </div>
</div>

<style lang=scss>
    $side-width: 20%;

    .projects {
        display: flex;
        width: 100%;

        .proj--left {
            width: $side-width;
            display: flex;
            flex-direction: column;

            :hover {
                cursor: pointer;
            }

            .proj--select {
                display: flex;
                width: 90%;
                padding: 20px 30px;
                background-color: rgb(43, 46, 81);
                border: 0;
                border-left: 3px solid #51588c;

                color: rgb(183, 186, 209);
                font-size: 1.3rem;
                font-weight: 400;

                transition: all 0.1s ease;

                &:hover {
                    cursor: pointer;
                    background-color: rgb(57, 62, 104);
                    color: rgb(211, 215, 248);
                }
            }
        }

        .proj--right {
            width: calc(100% - $side-width);
        }
    }

    .proj--selected {
        border-left: 5px solid #a5aef0 !important;
        background-color: rgb(57, 62, 104) !important;
        color: rgb(211, 215, 248) !important;
    }
    .proj--container { height: 100%; }

    @media only screen and (max-width: 1450px) {
        .proj--select {
            padding: 20px 15px !important;
        }    
    }
    @media only screen and (max-width: 1200px) {
        .proj--select {
            padding: 20px 5px !important;
        }    
    }

    // // Making selectors rows
    // @media only screen and (max-width: 700px) {
    //     .projects {
    //         flex-direction: column !important;
    //     }
    //     .proj--left {
    //         flex-direction: row !important;
    //         margin-bottom: 2rem !important;
    //         border: 0;
    //         // border-top: 3px solid #51588c !important;
    //     }
    //     .proj--selected {
    //         border-left: 0 solid !important;
    //         border-top: 5px solid #a5aef0 !important;
    //         background-color: rgb(57, 62, 104) !important;
    //         color: rgb(211, 215, 248) !important;
    //     }
    // }

    
</style>    