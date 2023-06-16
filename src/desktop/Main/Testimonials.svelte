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
        space-between="50"
        autoplay-delay="500"
        loop="true"
        autoplay-disable-on-interaction="false"
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
    >
    <swiper-slide style="background-color: #FFDAB9;">
        <h3>The one that <br> says I'm an <br> amazing <br> teammate</h3>
        <div class="testimonial__details">
            <div class="first--col">
                <img src="{Orangestar}" alt="">
                <p>Nneoma is an amazing team mate to work with. Her sense of intuition <br> and keenness to create designs that fit the user persona is one thing <br> that makes her stand out. Beyond working with Nneoma as a <br> designer, she is an amazing person with problem-solving abilities. You <br> can always be sure to get good and valid responses to any issues you <br> may be facing when you bring them to Nneoma.</p>
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

            <p> I am honoured to write a testimonial for Nneoma Okoro. Her incredible work <br> on the <a href="http://www.essentialrecruit.careers">essential recruit</a> platform continues to inspire me. <br> Not only does she possess immense talent and expertise, but she <br> consistently exhibits kindness, an eagerness to learn, and a delicate <br> commitment to delivering excellence. She is the first hire at ER and the <br> longest-serving member of our team and we are truly fortunate to have her. <br> 101% recommend her for any design project, she is an asset!</p>
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

            <p>I particularly like that Nneoma has an eye for how things can be better. <br> She doesn't get complacent and stuck in her creations. She is <br> constantly looking for ways to make sure we can create more value for <br> the users based on our vision and mission as a company.</p>
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

            <p>Dear Nneoma,  I wanted to take a moment to appreciate your tireless <br> efforts and unwavering dedication to the project. Your commitment <br> and hard work is unmatched. Thank you for everything you do. <br>
            With sincere appreciation. <br>
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

            <p>Nneoma is a versatile designer and working with her has been great. <br> She tries to review and understand the aim of a project and also <br> discusses with other team players. She delivers great results in time <br> and mixing creativity with her solid experience in designing, she <br> understand the needs and creates clean and usable designs.</p>
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
        padding: 5vw 0 5vw 3vw;

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
                    height: 100%;
                    padding: 5vw 2vw;
                    br{
                        display: none;
                    }

                    h3{
                        font-size: 5vw;
                        line-height: normal;
                    }
                }
            }
        }
    }
</style>