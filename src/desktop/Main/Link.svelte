<script>
     import MenuCta from "../../assets/say-hello-cta.svg"
     import MenuCtaWhite from "../../assets/say-hello-cta-white.svg"

     export let isWhite = false
</script>

{#if !isWhite}
<a href="mailto:nneomaokoro00@gmail.com"><img src="{MenuCta}" alt="say hello"></a>

{:else if isWhite}
<a href="mailto:nneomaokoro00@gmail.com"><img src="{MenuCtaWhite}" alt="say hello"></a>
{/if}


<style lang="scss">
       a{
            img{
                @include transition;
                object-fit: scale-down;
                &:hover{
                    transform: rotate(20deg);
                }
            }
        }
</style>