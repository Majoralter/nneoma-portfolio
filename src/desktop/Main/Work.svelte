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
                end: "bottom top"
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
</script>

<section class="work">
    <div class="work__screen">
        <h2><span class="splt-work">W</span><span class="splt-work">O</span><span class="splt-work">R</span><span class="splt-work">K</span></h2>
    </div>

    <div class="work__thumbnails">
        <div class="work__thumbnails--item one">
            <img src="{workOne}" alt="">

            <div class="work__details">
                <div class="work__details--desc">
                    <h3>Bridger</h3>
                    <p>Bridger is an end-to-end platform for B2B <br> payments and credit management.</p>
                </div>

                <!-- svelte-ignore a11y-invalid-attribute -->
                <a href="#">View Project <img src="{Arrow}" alt=""></a>
            </div>
        </div>
        <div class="work__thumbnails--item two">
            <img src="{workTwo}" alt="">

              <div class="work__details">
                <div class="work__details--desc">
                    <h3>Vendly</h3>
                    <p>Send and receive money using your <br> social media identity.</p>
                </div>

                <!-- svelte-ignore a11y-invalid-attribute -->
                <a href="#">View Project <img src="{Arrow}" alt=""></a>
            </div>
        </div>
        <div class="work__thumbnails--item three">
            <img src="{workThree}" alt="">

              <div class="work__details">
                <div class="work__details--desc">
                    <h3>Sposh Travels</h3>
                    <p>Enjoy the priviledge of selection from a <br> variety of packages that allow you embark on <br> a vacation and spread your bill payment.</p>
                </div>

                <!-- svelte-ignore a11y-invalid-attribute -->
                <a href="#">View Project <img src="{Arrow}" alt=""></a>
            </div>
        </div>
        <div class="work__thumbnails--item four">
            <img src="{workFour}" alt="">

              <div class="work__details">
                <div class="work__details--desc">
                    <h3>Smallworld</h3>
                    <p>Experience a connected world and stay up- <br> to-date while connecting with friends and <br> meeting new people on Smallworld</p>
                </div>

                <!-- svelte-ignore a11y-invalid-attribute -->
                <a href="#">View Project <img src="{Arrow}" alt=""></a>
            </div>
        </div>
        <div class="work__thumbnails--item five">
            <img src="{workFive}" alt="">

              <div class="work__details">
                <div class="work__details--desc">
                    <h3>Essential Recruit ER!</h3>
                    <p>We created a bridge that simplifies the process for nurses to find <br> workplaces and for healthcare systems to find incredible talent, and <br> provide resources to help them thrive in communities across Canada.</p>
                </div>

                <!-- svelte-ignore a11y-invalid-attribute -->
                <a href="#">View Project <img src="{Arrow}" alt=""></a>
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

        .work__thumbnails{
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            padding: 6vw;
            gap: 50px;

            .work__thumbnails--item{
                @include display-flex(column,center,center,1rem);
                width: fit-content;

                img{
                    object-fit: scale-down;
                }

                &::before{
                    z-index: -1;
                    opacity: .1;
                }

                .work__details{
                    width: 100%;
                    @include display-flex(row,flex-start,space-between,0);

                    a{
                        text-decoration: none;
                        font-size: 18px;
                        color: $cta-green;
                        font-weight: 500;
                        text-align: center;

                        img{
                            width: 18px;
                            height: auto;
                        }
                    }

                    .work__details--desc{
                        @include display-flex(column,flex-start,flex-start,1rem);

                        h3{
                            font-size: $h3;
                            font-family: $font-heading-body-menu;
                        }

                        p{
                            font-size: 16px;
                        }
                    }
                }
            }

            .one{
                // position: relative;
                img{
                    height: 495px;
                    width: auto;
                }

                &::before{
                    position: absolute;
                    top: -2.6rem;
                    left: 0;
                    content: "01";
                    color: $pastel-orange;
                    font-size: 250px;
                    font-family: $font-sub-heading-links;
                }
            }

            .two{
                position: relative;
                img{
                    height: 247.27px;
                    width: auto;
                }

                   &::before{
                    position: absolute;
                    top: -3rem;
                    left: -2.5rem;
                    content: "02";
                    color: $pastel-white;
                    font-size: 250px;
                    font-family: $font-sub-heading-links;
                }
            }

            .three{
                position: relative;
                img{
                    height: 295px;
                    width: auto;
                }

                   &::before{
                    position: absolute;
                    top: -2rem;
                    left: 0;
                    content: "03";
                    color: $pastel-pink;
                    font-size: 250px;
                    font-family: $font-sub-heading-links;
                }
            }

            .four{
                position: relative;
               img{
                    height: 638.89px;
                    width: auto;
               }

                  &::before{
                    position: absolute;
                    top: -10rem;
                    left: -2rem;
                    content: "04";
                    color: $orange;
                    font-size: 250px;
                    font-family: $font-sub-heading-links;
                }
            }

            .five{
                position: relative;
              img{
                  width: 971px;
                  height: auto;
              }

                 &::before{
                    position: absolute;
                    top: -10rem;
                    left: -5rem;
                    content: "05";
                    color: $pastel-green;
                    font-size: 250px;
                    font-family: $font-sub-heading-links;
                }
            }
        }
    }
</style>