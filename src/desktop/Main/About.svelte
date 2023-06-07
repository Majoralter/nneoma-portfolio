<script>
    import gsap from 'gsap'
    import ScrollTrigger from 'gsap/ScrollTrigger'
    import { onMount } from 'svelte';

    onMount(() =>{
        gsap.registerPlugin(ScrollTrigger);

        const tl = gsap.timeline({
            scrollTrigger: {
                trigger: ".about",
                pin: true,
                scrub: true,
                start: "top top",
                end: "bottom top"
            }
        });

        const text = gsap.utils.toArray(".splt")

        text.forEach(letter =>{
            tl.to(letter, {
                rotate: Math.floor(Math.random() * 90),
                y: 500,
                duration: 5
            })
        })

        tl.to('.about__screen', {
            ease: "ease",
            width: 0,
            duration: 10
        })
    })
</script>

<section class="about">
    <div class="about__screen">
        <h2><span class="splt">A</span><span class="splt">B</span><span class="splt">O</span><span class="splt">U</span><span class="splt">T</span></h2>
    </div>
</section>


<style lang="scss">
    .about{
        height: 200vh;
        position: relative;

        .about__screen{
            position: absolute;
            height: 50%;
            width: 100%;
            @include display-flex(column, center, center, 0);
            background-color: $black;
            overflow-y: hidden;
            

            h2{
             font-size: clamp(3vw, 40.625rem, 20vw);
             line-height: 770.25px;
             font-family: $font-sub-heading-links;
             white-space: nowrap;
             color: $white;

             span{
                display: inline-block;
                line-height: 770.25px;
             }
            }
        }
    }
</style>