<script>
    import MenuCta from "../assets/say-hello-cta.svg"
    import Logo from "../assets/logo.svg"
    import { fade,fly } from "svelte/transition"

    let menuActive = false

    const handleClick = () =>{
        menuActive = !menuActive
    }

    let viewportWidth = window.innerWidth

    window.addEventListener("resize", () =>{
        viewportWidth = window.innerWidth
    })
</script>


<nav>
    <ul>
        <li class="nav__link"><a href="../index.html"><img src="{Logo}" alt="logo"> Nneoma.okoro</a></li>
        <li class="nav__link"><button class="menu__toggle" on:click={handleClick}>MENU</button></li>
    </ul>
</nav>

{#if menuActive}
<div class="nav__menu" transition:fade>
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div class="nav__menu__close" on:click={handleClick}>
        <span class="nav__menu__close--item"></span>
        <span class="nav__menu__close--item"></span>
    </div>

    <div class="nav__menu__links">
        <div class="nav__menu__links--primary">
            <ul transition:fly="{{y: 100, duration: 1000}}">
                <li><a href="../index.html" class:active={menuActive}>Home</a></li>
                <!-- svelte-ignore a11y-invalid-attribute -->
                <li><a href="#">About</a></li>
                <!-- svelte-ignore a11y-invalid-attribute -->
                <li><a href="#">Work</a></li>
            </ul>
        </div>
        <div class="nav__menu__links--secondary" transition:fly="{{x: 100, duration: 1000}}">
            <p>
                Project? <br> Let's work
            </p>

            <a href="mailto:nneomaokoro00@gmail.com"><img src="{MenuCta}" alt="say hello"></a>
        </div>
    </div>
</div>
{/if}

<style lang="scss">
    nav{
        padding: 2.4375rem 7vw;
        font-family: $font-sub-heading-links;

        ul{
            @include display-flex(row,center,space-between,0);
            text-transform: uppercase;
            font-size: $a;
            list-style-type: none;

            li:first-of-type{
                a{
                    text-decoration: none;
                    color: $black;
                }
            }

            li:last-of-type{
                button{
                    background: none;
                    color: $black;
                    border: none;
                    font-family: $font-sub-heading-links;
                    font-size: $a;
                    cursor: pointer;
                }
            }
        }
    }

    .nav__menu{
        width: 100vw;
        height: 100vh;
        z-index: 1;
        position: fixed;
        top: 0;
        @include display-flex(column, center, center, 0);
        background-color: $white;
        font-family: $font-heading-body-menu;

        .nav__menu__close{
            position: absolute;
            margin: 0 auto;
            top: 2rem;
            outline: solid 3px $orange;
            border: dashed 2px $white;
            border-radius: 50%;
            height: 53px;
            width: 53px;
            background-color: $orange;
            cursor: pointer;
            @include display-flex(column, center, center, 0);
            @include transition;

            &:hover{
                transform: rotate(90deg);

                span{
                    width: 50%;
                }
            }

            .nav__menu__close--item{
                width: 40%;
                height: 3px;
                background-color: $white;
            }

            span:first-of-type{
                transform: rotate(45deg);
            }

            span:last-of-type{
                transform: rotate(-45deg) translate(2px, -2px);
            }
        }

        .nav__menu__links{
            @include display-flex(row, center, center, 0);
            width: 100%;

            .nav__menu__links--primary{
                padding: 5rem 7vw;
                border-right: solid 1px #EAEAEA;
                width: 50%;

                ul{
                  @include display-flex(column, center, center, 2rem);
                  list-style-type: none;

                  li{
                    a{
                        text-decoration: none;
                        font-size: $a-menu;
                        color: $black;
                        font-weight: bolder;
                        @include transition;

                      &:hover{
                        color: $green;
                        text-decoration: underline wavy 5px;
                       }

                       &.active{
                        color: $green;
                        text-decoration: underline wavy 5px;
                       }
                    }
                  }
                }
            }

            .nav__menu__links--secondary{
                @include display-flex(column, center, center, 1rem);
                width: 50%;
                text-align: center;

                p{
                    color: $black;
                    font-size: $a-menu;
                }

                a{
                    img{
                        @include transition;
                        object-fit: scale-down;
                        &:hover{
                            transform: rotate(20deg);
                        }
                    }
                }
            }
        }
    }
</style>