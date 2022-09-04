<script>
    import AboutMe from "$lib/components/AboutMe.svelte";
    import App from "../App.svelte";
</script>

<main>
    <div class="left">
        <div class="not--footer">
            <slot></slot>
        </div>
        <div class="footer">
            <a href="mailto:me@ntdi.world" target="_blank" class="container--email hunder">me@ntdi.world</a>
            <p class="container--links">
                <a href="https://github.com/professional-tdi" target="_blank" class="container--link hunder">Github</a> | <a href="https://www.spigotmc.org/members/ntdi.1414970/" target="_blank" class="container--link hunder">Spigot</a>
            </p>
        </div>
    </div>
    <div class="right">
        <div class="right--container">
            <AboutMe />
        </div>
    </div>
</main>

<style lang=scss>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@200;300;400;500;700&display=swap');
    $secondary-background: rgb(55, 58, 95);
    $background: #313452;

    main {
        display: flex;
        overflow-y: hidden;
        background-color: $secondary-background;
        .left {
            background-color: $background;
            width: 70%;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            .not--footer {
                width: 100%;
                display: flex;
                justify-content: center;
                // align-items: center;
            }

            .footer {
                display: none;  
                justify-content: center;
                align-items: center;
                flex-direction: column;
                padding: 30px 0;
                background-color: $secondary-background;
                width: 100%;
                .container--email {
                    text-decoration: none;
                    color: #97a3fd;
                    font-size: 1.5rem;
                }
                .container--links {
                    margin: 0;
                    margin-top: 20px;
                    color: rgb(211, 215, 248);
                    font-size: 1.5rem;
                    .container--link {
                        text-decoration: none;
                        color: #97a3fd;
                    }
                }
            }
        }
        .right {
            
            width: 30%;
            background-color: $secondary-background;
            height: 100vh;
            position: sticky;
            top: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            // border-left: 2px solid #5a608b;
            // box-shadow: rgba(0, 0, 0, 0.67) 0 0px 3px 1px;
            .right--container {
                height: 80%;
                width: 70%;
            }
        }
    }

    @media only screen and (max-width: 850px) {
        .left {
            width: 100% !important;
            background-color: $background !important;
        }
        .right {
            display: none !important;
        }
        .footer {
            display: flex !important;
        }
    }
    
</style>