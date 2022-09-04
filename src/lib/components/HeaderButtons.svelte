<script>
    import Fa from 'svelte-fa'
    import { faRectangleList, faHome } from '@fortawesome/free-solid-svg-icons'

    export let homeClick = () => {
        
    }
    export let projectClick = () => {
        
    }

</script>
<!-- <Fa icon={faCalendarAlt} /> -->

<div class="container">
    <div class="content">
        <div class="icon-container">
            <div class="icon icon-fill" on:click={() => homeClick()}>
                <i><Fa icon={faHome}/></i>
            </div>
            <div class="icon icon-collapse" on:click={() => projectClick()}>
                <i><Fa icon={faRectangleList}/></i>
            </div>
        </div>
    </div>
</div>

<style lang=scss>
    $icon-size	  : 4.5rem;
    $border-radius: 0.50;//15% = 0.15, 50% = 0.50 etc.

    $background   : #3b406a;
    $background-b : #3b406a;

    // Icon Colors
    $b-color      : #7881c7;

    // Text
    $white		  : rgb(211, 215, 248);
    $black		  : rgb(47, 48, 54);

    .container {
        margin-bottom: 4rem;
        user-select: none;
    }

    .content{
        display: table-cell;
        text-align: center;
        vertical-align: middle;
    }

    .icon-container{
        width: 100%;
        height: $icon-size;
    }

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

    .icon-fill{
        &::before{
            transition-duration: 0.4s;
            box-shadow: inset 0 0 0 0 $b-color;
            color: $black;
        }
        &:hover::before{
            box-shadow: inset 0 0 0 $icon-size $b-color;
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

    .icon-expand{
        &::after{
            box-shadow: inset 0 0 0 0 $b-color;
        }
        &::before{
            background: $b-color;
            box-shadow: inset 0 0 0 $icon-size $background;
        }
        &:hover::before{
            box-shadow: inset 0 0 0 0 $background;
        }
    }

    .icon-collapse{
        &::before{
            border-radius: 0;
        }
        &:hover::before{
            box-shadow: 
            inset 0 calc($icon-size/2) 0 0 $b-color,
            inset 0 calc($icon-size/-2) 0 0 $b-color;
        }
        &::after{
            box-shadow: inset 0 0 0 0 $b-color;
        }
    }

    .icon-rotate{
        box-shadow: inset 0 0 0 0 $b-color;
        &::after, &::before{
            border: 0px solid transparent;
        }
        &:hover::before{
            transition:
                border-top-width 0.3s ease,
                border-top-color 0.3s ease;
            border-width: $icon-size;
            border-top-color: $b-color ;
        }
        &:hover::after{
            transition:
                border-left-width 0.3s ease,
                border-left-color 0.3s ease;
            border-width: $icon-size;
            border-left-color: $b-color ;
        }
        &:hover{
            transition: background 0.001s ease 0.3s;
            background: $b-color ;
        }
        i{
            z-index: 1;
        }
    }
</style>