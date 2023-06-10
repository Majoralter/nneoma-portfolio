<script>
    import Magic from "../../assets/01Hero Section Magic (1).png"
    import Work from "../../assets/02 Hero Section Work.png"

    let viewportWidth = window.innerWidth

    window.addEventListener("resize", () =>{
        viewportWidth = window.innerWidth
    })
</script>

<section class="hero" id="hero">
    <h1>UI/UX DESIGNER</h1>

    <div class="hero__section">
        {#if viewportWidth >=768}
        <div class="hero__section--left">
            <img src="{Magic}" alt="">
            <h3>MAGIC.</h3>
            <p>
                Blank white screens were seen being turned <br> into user-friendly awesomeness. <br> It's not magic, she said.
            </p>

            <h6>
                -Page, scroll down for more tea
            </h6>
        </div>
        {/if}
        <div class="hero__section--mid">
            <h2>
                SOME AMAZING STUFF.
            </h2>
            <h3>
                You're reading a quick rundown of <br> Nneoma Okoro's work. Reach out, <br> let's create magic.
            </h3>
            <h6>
                You may be for a while
            </h6>
        </div>
        {#if viewportWidth >=768}
        <div class="hero__section--right">
            <img src="{Work}" alt="">
            <h3>WHAT I'VE WORKED ON.</h3>
            <p>
                Creative UI/UX Designer shares <br> highlights of some of her  projects with <br> accompanying Case Studies.
            </p>

            <h6>
                -Page, scroll down for more tea
            </h6>
        </div>
        {/if}
    </div>
</section>

<style lang="scss">
    .hero{
        @include display-flex(column, center, center, 3rem);
        height: 90vh;
        background-color: $white;
        h1{
            color: $black;
            font-size: $h1;
            font-family: $font-heading-body-menu;
            letter-spacing: -10;
            text-align: center;
        }

        .hero__section{
            @include display-flex(row,center,center,5vw);
            width: fit-content;



            .hero__section--left,.hero__section--right{
                @include display-flex(column,flex-start,flex-start,.7rem);
                color: $black;
                padding: 0 3vw;

                img{
                    height: 164px;
                    width: 100%;
                    object-fit: cover;
                }

                h3{
                    font-size: $h3;
                    font-family: $font-sub-heading-links;
                }

                p{
                    font-size: $p;
                    font-family: $font-heading-body-menu;
                }

                h6{
                    font-size: $tag;
                    font-family: $font-heading-body-menu;
                }
            }

            .hero__section--left{
                border-right: solid 1px #EAEAEA;
            }
            .hero__section--right{
                border-left: solid 1px #EAEAEA;
            }

            .hero__section--mid{
                @include display-flex(column, center, center, 2rem);
                text-align: center;
                color: $black;

                h2{
                    font-size: $h2;
                    font-family: $font-sub-heading-links;
                }

                h3{
                    font-size: $p;
                    font-family: $font-heading-body-menu; 
                }

                 h6{
                    font-size: $tag;
                    font-family: $font-heading-body-menu;
                }
            }
        }
    }

    @media (max-width: 768px){
        .hero{
            height: 100vh;
            padding: 5vw;
            @include display-flex(column, center, flex-start, 2rem);
        }
    }
</style>