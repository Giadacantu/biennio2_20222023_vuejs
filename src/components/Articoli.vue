<script setup>

</script>

<template>
    <div>
        <div class="articoli">
            <div class="container">
                <div class="content-articoli">
                    <div class="main-articolo">
                        <div class="img-container">
                            <img src="@/assets/images/1.png" alt="">
                            <div class="img-content">
                                <span>
                                    Articolo
                                </span>
                                <h3>
                                    Agisci ora!
                                </h3>
                            </div>
                        </div>
                    </div>
                    <div class="category-articoli">
                        <div class="top">
                            <div class="img-container">
                                <img src="@/assets/images/2.png" alt="">
                                <div class="img-content">
                                    <span>
                                        Articolo
                                    </span>
                                    <h3>
                                        Cosa respiriamo?
                                    </h3>
                                </div>
                            </div>
                            <div class="img-container">
                                <img src="@/assets/images/3.png" alt="">
                                <div class="img-content">
                                    <span>
                                        Articolo
                                    </span>
                                    <h3>
                                        Il green necessario
                                    </h3>
                                </div>
                            </div>
                        </div>
                        <div class="bottom">
                            <div class="img-container">
                                <img src="@/assets/images/4.png" alt="">
                                <div class="img-content">
                                    <span>
                                        Articolo
                                    </span>
                                    <h3>
                                        Insieme possiamo fare la differenza
                                    </h3>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="extra">
                    <div v-for="n in 3" :key="n" class="servizi">
                        <span class="icon">
                            <svg width="40" height="40" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path
                                    d="M15.2203 38.75C15.0109 38.7502 14.8039 38.7045 14.614 38.6162C14.4241 38.5278 14.2559 38.399 14.1211 38.2386C13.9864 38.0783 13.8883 37.8905 13.8339 37.6882C13.7795 37.486 13.7701 37.2743 13.8062 37.068V37.0594L16.0023 25H7.49999C7.26399 25 7.03282 24.9331 6.83321 24.8072C6.63361 24.6813 6.47373 24.5015 6.37206 24.2885C6.27039 24.0755 6.23109 23.8381 6.25871 23.6037C6.28633 23.3694 6.37973 23.1476 6.52811 22.9641L23.6508 1.79688C23.8457 1.54947 24.1162 1.37271 24.4211 1.29363C24.726 1.21455 25.0483 1.23749 25.3389 1.35895C25.6295 1.48041 25.8723 1.69371 26.0302 1.96622C26.1881 2.23873 26.2524 2.55546 26.2133 2.86797C26.2133 2.89141 26.207 2.91406 26.2031 2.9375L23.9992 15H32.5C32.736 15 32.9672 15.0669 33.1668 15.1928C33.3664 15.3187 33.5263 15.4985 33.6279 15.7115C33.7296 15.9245 33.7689 16.1619 33.7413 16.3963C33.7137 16.6307 33.6202 16.8524 33.4719 17.0359L16.3469 38.2031C16.2123 38.3731 16.0411 38.5106 15.8461 38.6053C15.651 38.7 15.4371 38.7494 15.2203 38.75Z"
                                    fill="#6C8D5A" />
                            </svg>

                        </span>
                        <div class="details">
                            <h6>Green wind</h6>
                            <p>La corsa contro il tempo per un futuro sostenibile</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.artcoli {
    border-bottom: 2px solid;
    margin: 100px;
}

.artcoli .container {
    max-width: calc(1440px -130px);
    padding: 0 20px;
    width: 100%;
    margin: 0px 0px;
}

.content-articoli {
    display: flex;
    justify-content: space-between;
    padding: 40px 0px;
}

.content-articoli>div {
    flex: 0 0 calc(50% - 20px);
    max-width: calc(50% - 20px);
    width: 100%;
}

.img-container {
    position: relative;
    height: 100%;
    width: 100%;

}

.img-container img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.img-container .img-content {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background: #ffffff;
    border-radius: 4px;
    padding: 16px 32px;
    text-align: center;
}

.img-container span {
    font-weight: 600;
    font-size: 12px;
    line-height: 13px;
    color: black;
    opacity: 0.4;
    text-transform: uppercase;

}

.img-container h3 {
    font-weight: bold;
    font-style: oblique;
    font-size: 22px;
    line-height: 25px;
    color:#008e61;
    margin-top: 5px;
}

.category-articoli .top {
    display: flex;
    justify-content: space-between;
    margin-bottom: 30px;
}

.category-articoli .top>div {
    flex: 0 0 calc(50% - 20px);
    max-width: calc(50% - 20px);
    ;
    width: 100%;
}

.extra {
    display: flex;
    justify-content: space-between;
    margin-bottom: 30px;
    /* margin-left: 50px; */
}

.extra>div {
    flex: 0 0 calc(33.33% - 20px);
    max-width: calc(33.33% - 20px);
    ;
    width: 100%;
    display: flex;
    align-items: center;
}

.servizi .details {
    margin-left: 10px;
    margin-top: 40px;
}

.details h6 {
    font-weight: bolder;
    font-size: 15px;
    line-height: 13px;
    font-family: Helvetica;

}

.details p {
    font-weight: 500;
    font-size: 12px;
    font-family: Helvetica;
    line-height: 20px;
    opacity: 0.9;
    font-style: italic;
}

@media (max-width: 969px) {
    .content-articoli {
        flex-wrap: wrap;

    }

    .content-articoli>div {
        flex: 0 0 100%;
        max-width: 100%;
        margin-top: 20px;
    }
}

@media (max-width: 600px) {
    .category-articoli .top>div {
        flex: 0 0 100%;
        max-width: 49%;
        /* margin: 20px;     */
    }

    .category-articoli .top {
        flex-wrap: wrap;
    }

    .img-content h3 {
        font-size: 18px;
        line-height: 20px;
    }

    .extra {
        flex-wrap: wrap;
    }

    .extra>div {
        max-width: 100%;
        margin: 20px;
    }
}
</style>
