<script>
    import gsap from "gsap"
    import { onMount } from 'svelte';

    onMount(() =>{
        const text = gsap.utils.toArray(".txt")

           gsap.to(".loader", {
                width: 0,
                duration: 3
            })

           text.forEach(txt =>{
                gsap.to(txt, {
                rotate: Math.floor(Math.random() * 45),
                y:  Math.floor(Math.random() * 200),
                delay: 3,
                duration: 1,
                ease: "bounce"
            })
           })

            gsap.to(".loading__screen", {
                height: 0,
                delay: 4,
                duration: 1,
            })
    })
</script>

<div class="loading__screen">
    <h3><span class="txt">N</span><span class="txt">N</span><span class="txt">E</span><span class="txt">O</span><span class="txt">M</span><span class="txt">A</span></h3>

    <div class="loader"></div>
</div>


<style lang="scss">
    .loading__screen{
        height: 100vh;
        width: 100vw;
        padding: 0;
        background-color: $black;
        position: fixed;
        z-index: 3;
        @include display-flex(column, center,center, 0);
        overflow: hidden;

        h3{
            color: $white;
            font-size: 5rem;
            font-family: $font-sub-heading-links;

            span{
                display: inline-block;
            }
        }

        .loader{
            height: 4px;
            width: 20%;
            background-color: $orange;
            border-radius: 7px;
        }
    }
</style>