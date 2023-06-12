<script>
    import gsap from 'gsap'
    import ScrollTrigger from 'gsap/ScrollTrigger'
    import { onMount } from 'svelte';

    onMount(() =>{
        gsap.registerPlugin(ScrollTrigger);

        const mm = gsap.matchMedia()

        const text = gsap.utils.toArray(".splt-work")

        mm.add("(min-width: 1024px)", () =>{
                 const tl = gsap.timeline({
            scrollTrigger: {
                trigger: ".work",
                pin: true,
                scrub: true,
                start: "top top",
            }
        });

            text.forEach(letter =>{
            tl.to(letter, {
                rotate: Math.floor(Math.random() * 90),
                y: 500,
                duration: 3
            }, 3)
        })

        tl.to('.work__screen', {
            ease: "none",
            x: "-100vw",
            delay: 2,
            duration: 2
        })
        })
    })

    import workOne from "../../assets/03 Work section Bridger(01).png"
    import workTwo from "../../assets/04 Work section Vendly (02).png"
    import workThree from "../../assets/05 Work section Sposh Travels (03).png"
    import workFour from "../../assets/06 Work Section Smallworld (04).png"
    import workFive from "../../assets/07 Work section ER (05).png"
    import Arrow from "../../assets/arrow.svg"

      let viewportWidth = window.innerWidth;
    window.addEventListener("resize", () =>{
        viewportWidth = window.innerWidth
    })
</script>

<section class="work">
    {#if viewportWidth >= 1024}
    <div class="work__screen">
        <h2><span class="splt-work">W</span><span class="splt-work">O</span><span class="splt-work">R</span><span class="splt-work">K</span></h2>
    </div>
    {/if}

    {#if viewportWidth <1024}
    <h4>Work</h4>
    {/if}

    <div class="work__items">
        <div class="work__items--item">
            <img src="{workOne}" alt="">

            <div class="work__items--detail">
                <h3>Bridger</h3>
                <a href="https://www.notion.so/Bridger-Boosts-B2B-Efficiency-A-Case-Study-fee300a5490b4429850bc55879e94ea8?pvs=4">View Project <img src="{Arrow}" alt=""></a>

                <p>
                    Bridger is an end-to-end platform for B2B <br> payments and credit management.
                </p>
            </div>
        </div>
        <div class="work__items--item">
            <img src="{workTwo}" alt="">

                 <div class="work__items--detail">
                <h3>Vendly</h3>
                <a href="https://www.notion.so/Vendly-b112b36420cb46b1bcb1ba729972b9ef?pvs=4">View Project <img src="{Arrow}" alt=""></a>

                <p>
                   Send and receive money using your <br> social media identity.
                </p>
            </div>
        </div>
        <div class="work__items--item">
            <img src="{workThree}" alt="">

                <div class="work__items--detail">
                <h3>Sposh Travels</h3>
                <a href="https://www.notion.so/Travel-Now-Pay-Later-9f3b3dcf668a437ea26508c08243ae2b?pvs=4">View Project <img src="{Arrow}" alt=""></a>

                <p>
                   Enjoy the priviledge of selection from a <br> variety of packages that allow you embark on <br> a vacation and spread your bill payment.
                </p>
            </div>
        </div>
        <div class="work__items--item">
            <img src="{workFour}" alt="">

                <div class="work__items--detail">
                <h3>Smallworld</h3>
                <a href="https://www.notion.so/Smallworld-98c42fb1a41d440795162a8f9e73d67e?pvs=4">View Project <img src="{Arrow}" alt=""></a>

                <p>
                Experience a connected world and stay up- <br> to-date while connecting with friends and <br> meeting new people on Smallworld
                </p>
            </div>
        </div>
        <div class="work__items--item five">
            <img src="{workFive}" alt="">

            
                <div class="work__items--detail">
                <h3>Essential Recruit ER!</h3>
                <a href="https://www.notion.so/Bridging-the-gap-ER-s-global-impact-on-Nursing-Recruitment-in-Canada-0f335e25579e4717bd1bbc6850e92fb8?pvs=4">View Project <img src="{Arrow}" alt=""></a>

                <p>
                We created a bridge that simplifies the process for nurses to find <br> workplaces and for healthcare systems to find incredible talent, and  provide resources to help them thrive in communities across Canada.
                </p>
            </div>
        </div>
    </div>
</section>

<style lang="scss">
    .work{
        height: fit-content;
        background-color: $black;
        position: relative;

        .work__screen{
            position: absolute;
            height: 100vh;
            width: 100vw;
            @include display-flex(column, center, center, 0);
            background-color: $black;
            overflow: hidden;
            z-index: 2;

              h2{
             font-size: 40vw;
             line-height: 770.25px;
             font-family: $font-sub-heading-links;
             white-space: nowrap;
             color: #343434;

             span{
                display: inline-block;
                line-height: 770.25px;
             }
            }
        }

         h4{
                color: #434343;
                font-family: $font-sub-heading-links;
                font-size: 10vw;
            }

        .work__items{
            display: grid;
            place-items: center;
            grid-template-columns: repeat(auto-fill, minmax(600px,1fr));
            height: fit-content;
            gap: 5vw;
            
            .work__items--item{
                height: fit-content;
                width: 460px;
                img{
                    width: 100%;
                    height: 50%;
                    object-fit: scale-down;
                    cursor: pointer;

                    &:hover{
                        scale: 0.99;
                        @include transition;
                    }
                }
            }

            .work__items--detail{
                @include display-flex(row,center,space-between,.7rem);
                flex-wrap: wrap;
                color: $white;

                a{
                    @include display-flex(row,center,center,.3rem);
                    white-space: nowrap;
                    text-decoration: none;
                    color: $cta-green;
                }

                h3{
                    font-size: 28px;
                    font-family: $font-heading-body-menu;
                }

                p{
                    font: 16px;
                    line-height: 23px;
                }
            }
        }
    }

    @media (max-width: 475px){
        .work{
            @include display-flex(column,center,center,1.5rem);
            .work__items{
                padding: 0;
                gap: 50px;
                .work__items--item{
                    width: 75vw;
                    padding: 2vw;
                    background-color: #343434;
                    border-radius: 1rem;
                    img{
                        border-radius: inherit;
                    }
                }


                .work__items--detail{
                    p{
                        white-space: normal;

                        br{
                            display: none;
                        }
                    }
                }
            }
        }
    }
</style>