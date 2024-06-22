<template>
    <div class="hero section">
        <img src="../assets/images/image-hero-desktop.png" alt="image-hero-desktop" class="hero-desktop img-cover">
        <img src="../assets/images/image-hero-mobile.png" alt="image-hero-mobile" class="hero-mobile img-cover">

        <div class="hero-content">
            <h1 class="title-content">Make remote work</h1>
            <p class="text-content">
            Get your team in sync, no matter your location. Streamline processes, 
            create team rituals, and watch productivity soar.</p>
            <button class="btn-primary">Learn more</button>

            <div class="client-list">
                <img src="../assets/images/client-databiz.svg" alt="client-databiz" class="img-client img-cover">
                <img src="../assets/images/client-audiophile.svg" alt="client-audiophile" class="img-client img-cover">
                <img src="../assets/images/client-meet.svg" alt="client-meet" class="img-client img-cover">
                <img src="../assets/images/client-maker.svg" alt="client-maker" class="img-client img-cover">
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Hero",
    data() {}
}
</script>

<style scoped>
    .hero { 
        max-width: 1150px;
        margin: 0 auto;
        width: 100%;
        position: relative;
        z-index: 5;
    }
    .hero {
        display: grid;
        grid-template-columns: repeat(1, 1fr);
        gap: 30px;
    }
    .hero .hero-desktop { display: none; }

    .hero .hero-content { 
        text-align: center; 
        padding-inline: 16px;
    }
    .hero .hero-content .title-content {
        margin-bottom: 15px;
        font-size: 1.8rem;
        font-weight: 700;
    }
    .hero .hero-content .text-content {
        color: var(--Medium-Gray);
        line-height: 1.6;
        font-size: 16px;
        font-weight: 600;
        margin-bottom: 20px;
    }
    .hero .hero-content .btn-primary {
        background-color: var(--Almost-Black);
        border: 2px solid transparent;
        color: var(--Almost-White);
        border-radius: 18px;
        padding: 15px 30px;
        font-size: 1.1rem;
        font-weight: 500;
        margin: 0 auto 40px;
        transition: .4s;
    }
    .hero .hero-content .btn-primary:hover {
        border: 2px solid var(--Almost-Black);
        background-color: transparent;
        color: var(--Almost-Black);
        transition: .4s;
    }
    .hero .client-list {
        display: flex;
        align-items: center;
        justify-content: space-between;
        gap: 20px;
    }
    .hero .client-list .img-client {
        width: 65px;
        height: auto;
    }

    /*---------------------------------------*\
      #MEDIA
    \*---------------------------------------*/

    /**
     * fit size 992px
     */
    @media screen and (min-width: 992px) {
        .hero {
            display: flex;
            align-items: center;
            justify-content: space-between;
            flex-direction: row-reverse;
            height: 100vh;
            width: 100%;
            gap: 100px;
        }
        .hero .hero-desktop { 
            display: block; 
            width: 600px;
            max-width: 550px;
        }
        .hero .hero-mobile { display: none; }

        .hero .hero-content { 
            text-align: left; 
            padding-inline: 0;
        }
        .hero .hero-content .title-content {
            margin-bottom: 30px;
            font-size: 5rem;
        }
        .hero .hero-content .text-content {
            font-weight: 500;
            width: 500px;
            font-size: 1.1rem;
            margin-bottom: 30px;
        }
        .hero .hero-content .btn-primary {
            padding: 15px 35px;
            margin: 0 0 80px; 
        }
        .hero .client-list .img-client { width: auto; }
    }
</style>