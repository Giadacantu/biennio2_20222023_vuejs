<script setup>

</script>

<template>
    <section class="subscribe-section">
        <div class="subscribe-wrapper">
            <h6 class="tobecentered">NEWSLETTER</h6>
            <h3 class="tobecentered">Iscriviti al blog e <br><span>resta aggiornato! </span></h3>
            <input type="text" placeholder="inserisci la tua email" class="tobecentered">
            <br><button class="btn tobecentered"> Iscriviti </button>
            <div class="img-container grafica">
                <img src="@/assets/images/Grafica.png" alt="">
            </div>
        </div>


    </section>
</template>


<style scoped>
section {
    background: #A8BBB7;
    padding: 60px 20px;

}

.subscribe-wrapper {
    max-width: 800px;
    width: 100%;
    margin: auto;
    background: #fff;
    position: relative;
}

.subscribe-wrapper .img-container {
    position: absolute;
    top: 0;
    bottom: 0;
    /* left: -50%; */
    right: auto;
}

.subscribe-wrapper .img-container img {
    height: 100.5%;
    margin-top: -1px;
}

.subscribe-wrapper {
    text-align: center;
    padding: 80px 0px;
}

.subscribe-wrapper h6 {
    font-size: 12px;
    font-weight: 600;
    line-height: 13px;
    opacity: 0.4;
    font-family: Helvetica;
    margin-left: 540px;
}

.subscribe-wrapper h3 {
    font-size: 24px;
    font-weight: 600;
    line-height: 35px;
    max-width: 282px;
    font-family: Helvetica;
    margin-left: 430px;
    text-align: right;
    color: #2D403A;
    margin-bottom: 30px;
}

.subscribe-wrapper h3 span {
    font-size: 30px;
    color: #62cfa6;
    font-family: Helvetica;
    font-weight: bold;
}

.subscribe-wrapper input {
    height: 64px;
    max-width: 340px;
    background-color: #e6e6e6;
    text-align: center;
    border: none;
    outline: none;
    width: 30%;
    margin-left: 380px;
    margin-bottom: 20px;

}

.subscribe-wrapper .btn {
    width: 140px;
    max-width: 340px;
    height: 50px;
    font-size: 12px;
    background-color: #2D403A;
    /* margin: auto; */
    text-transform: uppercase;
    color: #fff;
    border-radius: 0%;
    margin-left: 480px;

}

.subscribe-wrapper .btn:hover {
    background-color: #A8BBB7;
}

@media (max-width: 969px) {
    .subscribe-wrapper .img-container {
        display: none;
    }

    .subscribe-wrapper .tobecentered {
        margin-left: auto;
        margin-right: auto;
        width: 100%;
        text-align: center;
    }


}

@media (max-width: 600px) {
    .subscribe-wrapper {

        padding: 80px 20px;
    }

    section {
        padding: 60px 20px;
    }
}

@media(max-width: 400px) {
    .subscribe-wrapper h3 {
        font-size: 16px;
        line-height: 20px;
    }

    .subscribe-wrapper input,
    .subscribe-wrapper .btn {
        height: 40px;

    }
}
</style> 