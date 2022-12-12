<script>

</script>

<div class="container">
    <div class="container--top">
        <img src="/images/me.png" alt="" class="container--img">
        <h3 class="container--title">Ntdi</h3>
        <p class="container--blurb">Java and Web Engineer</p>
        <hr class="container--hr">
    </div>
    <div class="container--bottom">
        <a href="mailto:me@ntdi.world" target="_blank" class="container--email hunder">me@ntdi.world</a>
        <p class="container--links">
            <a href="https://github.com/n-tdi" target="_blank" class="container--link hunder">Github</a> | <a href="https://www.spigotmc.org/members/ntdi.1414970/" target="_blank" class="container--link hunder">Spigot</a>
        </p>
    </div>
</div>

<style lang=scss>
    .container {
        .container--top {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;

            .container--img {
                width: 65%;
                height: 65%;
                border-radius: 50%;
                // border: 2px solid #000000;
                // border-color: #5a608b;
                background-color: #2b2f49;
                padding: 10px;
                box-shadow: rgba(0, 0, 0, 0.67) 0 0 5px 2px;
                // box-shadow: rgba(0, 0, 0, 0.67) 3px 2px 1px;
                &:hover {
                    transform: rotate(-9000deg);
                    transition: all 6s ease-in-out;
                }
            }

            .container--title {
                color:rgb(211, 215, 248);
                font-size: 4rem;
                margin: 0 0;
                margin-top: 2rem;
                // text-shadow: black 5px 1px 1px;
            }

            .container--blurb {
                color: rgb(211, 215, 248);
                font-size: 1.6rem;
                margin: 0;
                margin-top: 30px;
                font-weight: 500;
            }

            .container--hr {
                width: 90%;
                margin-top: 30px;
                color: rgb(211, 215, 248);
                opacity: 50%;
                border-radius: 50%;
            }
        }
        .container--bottom {
            display: flex;  
            justify-content: center;
            align-items: center;
            flex-direction: column;
            padding-top: 30px;
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

    .hunder:hover {
        text-decoration: underline !important;
    }

    @media only screen and (max-width: 1300px) {
        .container--title {
            margin-top: 1rem !important;
            font-size: 3rem !important;
            
        }
        .container--blurb {
            margin-top: 20px !important;
        }
    }

    @media only screen and (max-width: 1000px) {
        .container--title {
            margin-top: 1rem !important;
            font-size: 2rem !important;
        }
        .container--blurb {
            margin-top: 15px !important;
        }
    }
</style>
