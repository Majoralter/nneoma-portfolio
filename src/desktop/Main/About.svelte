<script>
    import gsap from 'gsap'
    import ScrollTrigger from 'gsap/ScrollTrigger'
    import { onMount } from 'svelte';
    import Link from './Link.svelte';
    import { fade } from 'svelte/transition'

    onMount(() =>{
        gsap.registerPlugin(ScrollTrigger);

        const mm = gsap.matchMedia()

        const text = gsap.utils.toArray(".splt")

        mm.add("(min-width: 1024px)", () =>{
                const tl = gsap.timeline({
                scrollTrigger: {
                trigger: ".about",
                pin: true,
                scrub: true,
                start: "top top",
                end: "bottom+=1000px top"
            }
             });

            text.forEach(letter =>{
            tl.to(letter, {
                rotate: Math.floor(Math.random() * 90),
                y: 500,
                duration: 3
            }, 3)
        })

        tl.to('.about__screen', {
            ease: "none",
            x: "-100vw",
            delay: 2,
            duration: 2
        })
        })
    })

    let viewportWidth = window.innerWidth

    window.addEventListener("resize", () =>{
        viewportWidth = window.innerWidth
    })

    let isVisible = false

    const handleThis = () =>{
        isVisible = !isVisible
    }
</script>

<section class="about" id="about">
    {#if viewportWidth >= 1024}
    <div class="about__screen">
        <h2><span class="splt">A</span><span class="splt">B</span><span class="splt">O</span><span class="splt">U</span><span class="splt">T</span></h2>
    </div>
    {/if}

    <div class="about__section--left">
    {#if viewportWidth <1024}
    <h4>About Me</h4>
    {/if}
    
    <h2>
        Design. <span>Design.</span>
    </h2>
    <h2>
        Music. <span>Sitcoms.</span>
    </h2>
    <h2>
        Design.
    </h2>

    <p>
        Hello! My name is Nneoma Okoro. I am a UI/UX Designer interested in creating seamless <br> user experiences that solve problems while maintaining a visually appealing interface to <br> engage users. After in-depth research and understanding of users' frustrations and <br> needs, I create design solutions to address them by simplifying complexity and <br> enhancing usability.
    </p>

 
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <p style="color: #44AB04; cursor: pointer;" on:click={handleThis} class:thisActive={isVisible}>Read more</p>
    </div>

    <div class="about__section--right">
        <Link isWhite = {true} />

        {#if isVisible}
        <p transition:fade>
            On the other hand, when I'm not designing, you'll catch me listening <br> to a lot of The Weeknd and Afrobeats. I also engage in playing <br> monopoly, scrabble and paintball sessions with friends. Oh, I watch a <br> lot of football and sitcoms! Friends, The Big Bang Theory, Young <br> Sheldon, How I Met Your Mother. So whether I'm crafting designs, <br> listening to amazing stuff, battling it out in games, cheering on my <br> favourite team or laughing at sitcoms, I'm always seeking inspiration <br> in the things that bring me alive.
        </p>
        {/if}
    </div>
</section>


<style lang="scss">
    .about{
        height: 100vh;
        position: relative;
        background-color: $black;
        padding: 3rem 1vw;
        @include display-flex(row, center, center, 0);

        .about__screen{
            position: absolute;
            height: 100%;
            width: 100%;
            @include display-flex(column, center, center, 0);
            background-color: $black;
            overflow: hidden;
            

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

        .about__section--left{
            @include display-flex(column, flex-start, flex-start, 1rem);

            h4{
                color: #434343;
                font-family: $font-sub-heading-links;
                font-size: 10vw;
            }

            h2{
                font-size: $font-size-xxxl;
                font-family: $font-heading-body-menu;
                white-space: nowrap;
            }

            h2:first-of-type{
                color: $pastel-orange;
                margin-left: 2vw;

                span{
                    color: $pastel-white;
                }
            }

            h2:nth-child(2){
                color: $pastel-green;

                span{
                    color: $pastel-pink;
                }
            }

            h2:last-of-type{
                margin-left: 1vw;
            }

            p{
                font-size: $p;
                font-family: $font-heading-body-menu;
                line-height: 34px;
                white-space: pre;
            }
        }

        .about__section--right{
            padding: 3vw;
            p{
                font-size: $p;
                font-family: $font-heading-body-menu;
                line-height: 34px;
                white-space: pre;
            }
        }
    }

    @media (max-width: 750px){
        .about{
            height: fit-content;
            br{
                display: none;
            }

            @include display-flex(column,center,center,0);

            .about__section--left{
                padding: 5vw;
                p{
                    white-space: normal;
                }
            }

            .about__section--right{
                padding: 5vw;
            @include display-flex(column-reverse,center,center,0);

            p{
                white-space: normal;
            }
            }
        }
    }
</style>