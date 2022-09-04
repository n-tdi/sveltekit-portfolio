<script>
    import Fa from 'svelte-fa'
    import { faLink } from '@fortawesome/free-solid-svg-icons'

    export let title
    export let languages 
    export let body
    export let githubURL

    body = body.split("*")
</script>

<div class="container">
    <div class="item">
        <div class="item--top">
            <div class="item--title__width">
                <a href={githubURL} target="_blank" class="item--btn underline">
                    <h3 class="item--title">{title} <i><Fa icon={faLink}/></i></h3> 
                </a>
            </div>
            <h6 class="item--languages">{languages}</h6>
            <div class="item--container">
                <ul class="item--ul">
                    {#each body as point}
                        <li class="item--li">
                            <div class="item--li__text">
                                {point}
                            </div>
                        </li> 
                    {/each}
                </ul>
            </div>
        </div>
        <!-- <div class="item--bottom">
            <a href={githubURL} target="_blank" class="item--btn">
                <div class="icon icon-enter"><i><Fa icon={faLink}/></i></div>
            </a>
        </div> -->
    </div>
</div>

<style lang=scss>
    // Text
    $white		  : rgb(211, 215, 248);

    .container {
        height: 100%;
    }

    .item {
        height: inherit;
        display: flex;
        flex-direction: column;
        margin-left: 1rem;

        .item--top {
            .item--title__width {
                display: inline-flex;
                .item--btn {
                    text-decoration: none;
                    .item--title {
                        color: $white;
                        font-size: 2.9rem;
                    }
    
                    &:hover {
                        .item--title {
                            transition: all 0.1s ease-in-out;
                            color: rgb(189, 192, 228);
                        }
                    }
                }
            }

            .item--languages {
                font-size: 1.2rem;
                color: #7881c7;
            }

            .item--container {
                padding-top: 2rem;
        
                .item--ul {
                    .item--li {
                        display: flex;
                        font-size: 1.3rem;
                        color: $white;
                        margin-bottom: 1rem;
                        list-style: none;
                        &::before {
                            content: ">";
                            color: #7881c7;
                            font-weight: 600;
                            margin-right: 1rem;
                        }
                    }
                }
            }
        }

        // .item--bottom {
        //     display: flex;
        //     align-items: center;
        //     justify-content: center;
        // }
    }

    .underline {
        position: relative;
        display: flex;

        &::after {
            content: '';
            position: absolute;
            width: 100%;
            transform: scaleX(0);
            height: 3px;
            bottom: 0;
            left: 0;
            background-color: rgba(189, 192, 228, 0.846);
            transform-origin: bottom right;
            transition: transform 0.25s ease-out;
        }
        &:hover::after {
            transform: scaleX(1);
            transform-origin: bottom left;
        }
    }

    $icon-size	  : 4rem;
    $border-radius: 0.50;//15% = 0.15, 50% = 0.50 etc.

    // Icon Colors
    $b-color      : #7881c7;

    .icon{
        cursor: pointer;
        position: relative;
        display: inline-block;
        width: $icon-size;
        height: $icon-size;
        margin-left: calc($icon-size/5);
        margin-right: calc($icon-size/5);
        border-radius: calc($icon-size*$border-radius);
        overflow: hidden;
        box-shadow: rgba(0, 0, 0, 0.67) 2px 1px 1px;
        border: 0 solid;
        &::before, &::after{
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            height: 100%;
            width: 100%;
            transition: all 0.25s ease;
            border-radius: calc($icon-size*$border-radius);
        }
        i {
            position: relative;
            color: $white;
            font-size: calc($icon-size/2);
            margin-top: calc($icon-size/4);
            transition: all 0.25s ease;
            display: flex;
            justify-content: center;
            
        }
    }

    .icon-enter{
        &::after{
            box-shadow: inset 0 0 0 0 $b-color;
        }
        &::before{
            border-radius: 0;
            margin-left: -100%;
            box-shadow: inset 0 0 0 $icon-size $b-color;
        }
        &:hover::before{
            margin-left: 0;
        }
    }
</style>