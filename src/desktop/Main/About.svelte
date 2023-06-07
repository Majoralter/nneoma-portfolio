<script>
    import gsap from 'gsap'
    import ScrollTrigger from 'gsap/ScrollTrigger'
    import { onMount } from 'svelte';
    import Link from './Link.svelte';

    onMount(() =>{
        gsap.registerPlugin(ScrollTrigger);

        const tl = gsap.timeline({
            scrollTrigger: {
                trigger: ".about",
                pin: true,
                scrub: true,
                start: "top top",
                end: "bottom+=500px top"
            }
        });

        const text = gsap.utils.toArray(".splt")

        text.forEach(letter =>{
            tl.to(letter, {
                rotate: Math.floor(Math.random() * 90),
                y: 500,
                duration: 1,
            }, 3)
        })

        tl.to('.about__screen', {
            ease: "none",
            x: "-100vw",
            delay: 2,
            duration: 2
        })
    })

    let viewportWidth = window.innerWidth;
    window.addEventListener("resize", () =>{
        viewportWidth = window.innerWidth
    })
</script>

<section class="about">
    {#if viewportWidth >=768}
    <div class="about__screen">
        <h2><span class="splt">A</span><span class="splt">B</span><span class="splt">O</span><span class="splt">U</span><span class="splt">T</span></h2>
    </div>
    {/if}

    <div class="about__section--left">
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
    </div>

    <div class="about__section--right">
        <Link />
    </div>
</section>


<style lang="scss">
    .about{
        height: 100vh;
        position: relative;
        background-color: $black;
        @include display-flex(row, center, center, 3rem);

        .about__screen{
            position: absolute;
            height: 100%;
            width: 100%;
            @include display-flex(column, center, center, 0);
            background-color: $black;
            overflow: hidden;
            

            h2{
             font-size: 40.625rem;
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

            h2{
                font-size: 3.90625rem;
                font-family: $font-heading-body-menu;
            }

            h2:first-of-type{
                color: $pastel-orange;
                margin-left: 50px;

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
                margin-left: 30px;
            }

            p{
                font-size: $p;
                font-family: $font-heading-body-menu;
                line-height: 34px;
            }
        }
    }
</style>