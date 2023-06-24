<script>
    import { register } from "swiper/element/bundle"
    register()

    import Greenstar from "../../assets/green-star.svg"
    import Orangestar from "../../assets/orange-star.svg"
    import Purplestar from "../../assets/purple-star.svg"

    import Link from "./Link.svelte"
</script>

<section class="testimonial">
    <div class="top--col">
        <h4>My teammates have a lot to say!</h4>

        <Link isWhite={true} />
    </div>

    <swiper-container
        slides-per-view="1.5"
        space-between="40"
        loop="true"
        speed="1200"
        breakpoints={{
            300:{
                slidesPerView: 1.1,
                spaceBetween: 30
            },
            1024: {
                slidesPerView: 1.5
            }
        }}

        grab-cursor="true"
    >
    <swiper-slide style="background-color: #FFDAB9;">
        <h3>The one that <br> says I'm an <br> amazing <br> teammate</h3>
        <div class="testimonial__details">
            <div class="first--col">
                <img src="{Orangestar}" alt="">
                <p>Nneoma is an amazing team mate to work with.  Beyond <br>  working with Nneoma as a designer, she is an amazing <br> person with problem-solving abilities.</p>
            </div>

            <p>
                - Samuel Olowookere, Product manager, Bridger.
            </p>
        </div>
    </swiper-slide>
    <swiper-slide style="background-color: #E6E6FA;">
                <h3>The one that <br> says I'm an <br> asset</h3>
        <div class="testimonial__details">
            <div class="first--col">
                <img src="{Purplestar}" alt="">

            <p> Nneoma's incredible work at ER continues to inspire me. <br> She possesses immense talent and expertise. She is the <br> first hire at ER and the longest-serving member of our team <br> and we are truly fortunate to have her. She is an asset!</p>
            </div>

            <p>
                - Daniel Morka, CPO & Co-Founder, Essential Recruit.
            </p>
        </div>
    </swiper-slide>
    <swiper-slide style="background-color: #B2D8B2;">
        <h3>The one that <br> says I always <br> create more <br> value</h3>
        <div class="testimonial__details">
            <div class="first--col">
                <img src="{Greenstar}" alt="">

            <p>I particularly like that Nneoma has an eye for how things can be better. <br> She doesn't get complacent and stuck in her creations. She is <br> constantly looking for ways to make sure we can create more value.</p>
            </div>

            <p>
                - Samuel Olowookere, Product manager, Bridger.
            </p>
        </div>
    </swiper-slide>
    <swiper-slide style="background-color: #FFDAB9;">
           <h3>The one that <br> is filled with <br> appreciation</h3>
        <div class="testimonial__details">
            <div class="first--col">
                <img src="{Orangestar}" alt="">

            <p>I appreciate her tireless efforts and unwavering dedication <br> to the project at Smallworld. Her commitment and <br>hard work is unmatched. <br>
            Olaiya.</p>
            </div>

            <p>
                - Olatunji Olaiya, Founder/CEO, Smallworld.
            </p>
        </div>
    </swiper-slide>
    <swiper-slide style="background-color: #E6E6FA;">
        <h3>Oh! This <br> one's from a <br> Developer</h3>
        <div class="testimonial__details">
            <div class="first--col">
                <img src="{Purplestar}" alt="">

            <p>Nneoma is a versatile designer and working with her has <br> been great. She discusses with other team players and <br> delivers great results in time.</p>
            </div>

            <p>
                - Taoheed Ogundeyi, Frontend Developer, Essential Recruit.
            </p>
        </div>
    </swiper-slide>
</swiper-container>
</section>

<style lang="scss">
    .testimonial{
        height: 100vh;
        background-color: $black;
        padding: 5vw 0 0 3vw;

        .top--col{
            @include display-flex(row, center, space-between, 0);
            margin-bottom: 2rem;

            h4{
                text-transform: uppercase;

                &::after{
                    content: "(You'd want to read these)";
                    font-weight: lighter;
                    margin-left: .3em;
                    text-transform: none;
                }
            }
        }

        swiper-container{
            height: 50%;

            swiper-slide{
                height: 100%;
                background-color: orange;
                @include display-flex(row, center, space-between, 0);
                padding: 2.8125rem 2.6875rem;

                h3{
                    font-size:  3vw;
                    font-family: $font-heading-body-menu;
                    color: $black;
                    font-weight: 700;
                    line-height: 59px;
                }

                .testimonial__details{
                    @include display-flex(column, flex-start, space-between, 0);
                    height: 80%;
                    .first--col{
                        @include display-flex(row,flex-start,flex-start,1em);
                    }

                    p{
                        font-size: 17px;
                        font-weight: 500;
                        color: $black;
                    }
                }
            }
        }
    }

    @media (max-width: 768px){
        .testimonial{
            height: 100vh;
            swiper-container{
                height: 70%;
                swiper-slide{
                    flex-direction: column;
                    height: 70%;
                    padding: 26px;
                    text-align: center;
                    justify-content: center;
                    gap: 3em;
                    br{
                        display: none;
                    }

                    h3{
                        font-size: 20px;
                        font-weight: bolder;
                        line-height: normal;
                        text-align: center;
                    }

                    .testimonial__details{
                        justify-content: center;
                        gap: 2em;
                        margin: 0;
                        height: fit-content;

                        .first--col{
                            p{
                                font-size: 14px;
                            }
                        }
                    }
                }
            }
        }
    }
</style>