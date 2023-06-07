<script>
     import MenuCta from "../../assets/say-hello-cta.svg"
</script>

<a href="mailto:nneomaokoro00@gmail.com"><img src="{MenuCta}" alt="say hello"></a>


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