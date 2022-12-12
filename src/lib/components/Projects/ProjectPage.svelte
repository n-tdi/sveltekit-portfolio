<script>
    import Project from "$lib/components/Projects/Project.svelte";
</script>

<div class="container">
    <div class="project">
        <h2 class="proj--title">PROJECTS</h2>
        <Project />
    </div>
    <div class="bad--size">
        <div class="bad--container">
            <h1 class="bad--size__title">Sorry, This page isn't available for your screensize.</h1>
        </div>
    </div>
</div>

<style lang=scss>
    .proj--title {
        color: #7881c7;
        margin-bottom: 3rem;
        font-size: 2.3rem;
    }

    .project {
        height: 72vh;
    }

    .bad--size {
        display: none;
    }

    @media only screen and (max-width: 510px) {
        .project {
            display: none !important;
        }

        .bad--size {
            display: flex !important;
            height: 63.7vh;
            margin-top: 5rem;
            color: rgb(211, 215, 248);
        }
    }
</style>