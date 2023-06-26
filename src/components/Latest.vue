<script setup>

</script>

<template>
    <section class="latest">
        <div class="container">
            <div class="latest-header">
                <h3>Recenti</h3>
                <a href="#">SEE ALL</a>
            </div>
            <div class="latest-wrapper">
                <div class="latest">
                    <div class="img-container">
                        <img src="@/assets/images/siccità.jpg" alt="">
                    </div>
                    <div class="latest-content">
                        <h4> Terra rugosa </h4>
                        <p>La siccità del terreno provoca aridità e screpolature, impedendo alle piante di ottenere le
                            risorse di cui hanno bisogno. Gli ecosistemi soffrono, con erba secca, alberi spogli e corpi
                            idrici ridotti a letti di fango. Questa condizione rappresenta una sfida per l'agricoltura e
                            richiede strategie di gestione idrica per preservare la risorsa dell'acqua.</p>
                    </div>
                </div>
                <div class="latest">
                    <div class="img-container">
                        <img src="@/assets/images/plastica.jpg" alt="">
                    </div>
                    <div class="latest-content">
                        <h4> Plasticqua </h4>
                        <p>La plastica nell'oceano minaccia la vita marina e gli ecosistemi. Milioni di tonnellate sono
                            scaricate ogni anno, causando danni irreversibili. Ridurre l'uso della plastica monouso e
                            promuovere soluzioni sostenibili è cruciale per proteggere gli oceani.</p>
                    </div>
                </div>
                <div class="latest">
                    <div class="img-container">
                        <img src="@/assets/images/smog.jpg" alt="">
                    </div>
                    <div class="latest-content">
                        <h4> Nuvole nere </h4>
                        <p>Lo smog è una miscela di inquinanti atmosferici derivati dalle emissioni industriali, veicolari e
                            domestiche, che compromette la qualità dell'aria. È una minaccia per la salute umana, causando
                            problemi respiratori e danni al sistema cardiovascolare. La lotta contro lo smog richiede
                            riduzione delle emissioni, promozione di energie rinnovabili e pratiche sostenibili.</p>
                    </div>
                </div>
            </div>
        </div>

    </section>
</template>

<style scoped>
.latest .latest-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 30px;
}

.latest-header h3 {
    font-weight: 600;
    font-size: 22px;
    line-height: 25px;
    margin-top: 50px;
}

.latest-header a {
    font-weight: 500;
    font-size: 9px;
    line-height: 13px;
    text-transform: uppercase;
    opacity: 0.5;
    text-decoration: none;
    color: black;
    margin-bottom: -100px;
}

img {
    width: 100%;
}

.latest-header a:hover {
    color: #A8BBB7;
}

.latest-wrapper {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 30px;
}

.latest .latest-content {
    max-width: calc(100% - 48px);
    width: 100%;
    margin: auto;
    transform: translateY(-100px);
    padding: 24px 16px;
    background-color: #fff;
}

.latest .latest-content h4 {
    color: #2D403A;
    font-size: 18px;
    font-weight: bold;
}

@media (max-width: 969px) {
    .latest-wrapper {
        grid-template-columns: 1fr 1fr;
    }

    .latest .latest-content {
        max-width: 100%;
        transform: translateY(0px);
    }

}

@media (max-width: 600px) {
    .latest-wrapper {
        grid-template-columns: 1fr;
    }
    .latest .latest-content {
        padding: 20px 20px;
    }
    .latest .img-container{
     padding: 20px 20px;
    }
    .latest-header h3{
        padding-left: 20px;
        margin-top: 50px;
    }
      .latest-header a{
        padding-right: 20px;
        margin-top: 30px;
    }
}
</style>