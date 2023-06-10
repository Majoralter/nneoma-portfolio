<script>
        import gsap from 'gsap'
    import ScrollTrigger from 'gsap/ScrollTrigger'
    import { onMount } from 'svelte';
    import Link from './Link.svelte';

    onMount(() =>{
        gsap.registerPlugin(ScrollTrigger);

        const tl = gsap.timeline({
            scrollTrigger: {
                trigger: ".work",
                pin: true,
                scrub: true,
                start: "top top",
                end: "bottom+=500px top"
            }
        });

        const mm = gsap.matchMedia()

        const text = gsap.utils.toArray(".splt-work")

        mm.add("(min-width: 1024px)", () =>{
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
</script>

<section class="work">
    <div class="work__screen">
        <h2><span class="splt-work">W</span><span class="splt-work">O</span><span class="splt-work">R</span><span class="splt-work">K</span></h2>
    </div>
</section>

<style lang="scss">
    .work{
        height: 100vh;
        position: relative;
        background-color: $orange;

        .work__screen{
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
    }
</style>