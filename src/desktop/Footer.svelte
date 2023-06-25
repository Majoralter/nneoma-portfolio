<script>
    import Emoji from "../assets/wave-emoji.svg"
    import Mailicon from "../assets/mail-icon.svg"
    import Behanceicon from "../assets/behance-icon.svg"
    import Twittericon from "../assets/twitter-icon.svg"
    import Instagramicon from "../assets/instagram-icon.svg"
</script>

<footer class="footer">
    <h3>
        Reach out, let's build <br> something amazing!
    </h3>

    <div class="footer__cta">
    <a href="mailto:nneomaokoro00@gmail.com">Hey! it's nice to meet you <img src="{Emoji}" alt=""></a>
    </div>

    <div class="social__links">
        <a href="mailto:nneomaokoro00@gmail.com"><img src="{Mailicon}" alt=""></a>
        <a href="https://twitter.com/jhenevieve_gold"><img src="{Twittericon}" alt=""></a>
        <a href="https://www.behance.net/nneomaokoro"><img src="{Behanceicon}" alt=""></a>
        <a href="http://instagram.com/jhenevieve_gold"><img src="{Instagramicon}" alt=""></a>
    </div>
</footer>

<style lang="scss">
    .footer{
        @include display-flex(column, center, center, 4rem);
        height: 100vh;
        background-color: $white;
        padding: 4vw;

        h3{
            font-size: $font-size-xxxl;
            color: $black;
            font-family: $font-heading-body-menu;
            text-align: center;
            line-height: normal;
        }

        .footer__cta{
            a{
            background-color: $black;
            padding: 10px 24px;
            border-radius: 8px;
            @include display-flex(row, center, center, 1em);
            color: $white;
            text-decoration: none;

            img{
                animation: wave infinite .3s alternate;
                @include transition;
            }

            @keyframes wave{
                0%{
                    transform: rotate(0);
                }
                100%{
                    transform: rotate(15deg);
                }
            }

            &:hover{
                box-shadow: 0px 16px 45px rgba(138, 138, 138, 0.2);
            }
        }
        }

        .social__links{
            @include display-flex(row, center, center, 3vw);

            a{
                @include transition;

                img{
                    object-fit: scale-down;
                }

                &:hover{
                    transform: translateY(-8px);
                }
            }
        }
    }

    @media (max-width: 768px){
        .footer{
            gap: 3.2rem;
            h3{
                br{
                    display: none;
                }
            }
        }
    }
</style>