<template>
    <div id="app">

        <transition name="fade">
            <div v-if="loadShow" id="preloader">
                <div id="status">
                    <div class="spinner">
                        <div class="rect1"></div>
                        <div class="rect2"></div>
                        <div class="rect3"></div>
                        <div class="rect4"></div>
                        <div class="rect5"></div>
                    </div>
                </div>
            </div>
        </transition>
        <!--  <ul id="menu">
            <li data-menuanchor="page1" class="active"><a href="#page1">Section 1</a></li>
            <li data-menuanchor="page2"><a href="#page2">Section 2</a></li>
            <li data-menuanchor="page3"><a href="#page3">Section 3</a></li>

        </ul> -->


        <!--  <ul class="actions">
            <li>
                <a class="actions-button" href="#" rel="noopener" @click="addSection">Add section</a>
            </li>
            <li>
                <a class="actions-button" href="#" rel="noopener" @click="removeSection">Remove section</a>
            </li>
            <li>
                <a class="actions-button" href="#" rel="noopener" @click="toggleNavigation">Toggle nav</a>
            </li>
            <li>
                <a class="actions-button" href="#" rel="noopener" @click="toggleScrollbar">Toggle scrollBar</a>
            </li>
        </ul> -->

        <full-page :options="options" id="fullpage" ref="fullpage">
            <div class="section">
                <div class="poe1">
                    <div class="caption">
                        <span class="poe1__caption-1">Seneler,seneler evveldi; </span> <br>
                        <span class="poe1__caption-2">Bir deniz ülkesinde</span> <br>
                        <span class="poe1__caption-3">Yaşayan bir kız vardı, bileceksiniz</span> <br>
                        <span class="poe1__caption-4">İsmi Annabel Lee;</span>
                    </div>
                </div>
            </div>


            <div class="section">
                <div class="poe2">
                    <div class="caption">
                        Hiçbir şey düşünmezdi sevilmekten <br>
                        Sevmekden başka beni. <br>
                        O çocuk ben çocuk, memleketimiz <br>
                        O deniz ülkesiydi,
                    </div>
                </div>
            </div>
            <div class="section">
                <div class="poe3">
                    <div class="caption">
                        Sevdalı değil karasevdalıydık <br>
                        Ben ve Annabel Lee; <br>
                        Göklerde uçan melekler bile <br>
                        Kıskanırdı bizi.

                    </div>
                </div>
            </div>
            <div class="section">
                <div class="poe4">
                    <div class="caption">
                        Bir gün işte bu yüzden göze geldi <br>
                        O deniz ülkesinde <br>
                        Üşüdü bir rüzgarından bulutun <br>
                        Güzelim Annabel Lee <br>

                    </div>
                </div>
            </div>

            <div class="section">

                <div class="introduction">
                    <h4><strong>İngilizce Aslı:</strong> Annabel Lee / Edgar Allan Poe</h4>
                    <p>- Çeviri : Melih Cevdet Anday</p>


                    <a href="https://www.github.com/fatihtuzunn" class="btn"> GitHub</a>

                    <p class="footer">Made with <i>fullPage.js</i> and <i>Midjourney</i> </p>
                </div>

            </div>




        </full-page>
    </div>
</template>

<script>

// Optional. When using fullpage extensions
// import './fullpage.scrollHorizontally.min'

export default {
    name: 'app',
    data() {
        return {
            loadShow: true,
            options: {
                licenseKey: 'YOUR_KEY_HERE',
                afterLoad: this.afterLoad,
                scrollOverflow: true,
                scrollBar: false,
                menu: '#menu',

                navigation: true,
                anchors: ['page1', 'page2', 'page3', 'page4', "page5"],
                sectionsColor: ['#41b883', '#ff5f45', '#0798ec', '#fec401', '#12242A']

            }
        }
    },
    mounted() {
        fullpage_api.setKeyboardScrolling(true)
        window.addEventListener('load', () => {
            this.loadShow = !this.loadShow;
        })


    },

    methods: {

        /* 
              afterLoad () {
                console.log('After load')
              },
        
             
              toggleNavigation () {
                this.options.navigation = !this.options.navigation
              },
              
              toggleScrollbar () {
                console.log('Changing scrollbar...')
                this.options.scrollBar = !this.options.scrollBar
              } */
    }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Lobster&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Courgette&display=swap');

@keyframes moveInLeft {

    /* Animaton start */
    0% {
        opacity: 0;
        transform: translateX(-10rem);

    }

    80% {
        transform: translateX(.8rem);
    }


    /* Animaton finish */
    100% {
        opacity: 1;
        transform: translate(0);
    }
}

@keyframes moveInRight {

    /* Animaton start */
    0% {
        opacity: 0;
        transform: translateX(10rem);

    }

    80% {
        transform: translateX(-.8rem);
    }


    /* Animaton finish */
    100% {
        opacity: 1;
        transform: translate(0);
    }
}


body {
    font-family: 'Courgette', cursive;

}

.introduction {
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    font-size: 25px;
    text-align: center;
    color: #f1f1f1;
}

.introduction>.btn {
    font-size: 15px;
    background-color: #eee;
    display: inline-block;
    width: 5rem;
    height: 2rem;
    border-radius: 5rem;
    border: none;
    padding: .4rem;
    margin-top: 5rem;
}

.introduction>.btn:hover {
    box-shadow: 2px 4px 6px rgba(153, 142, 142, 0.5);
}

.footer {
    font-size: 15px;
    display: block;
    position: relative;
    top: 100%;
}

.poe1,
.poe2,
.poe3,
.poe4,
.poe5 {

    background-size: cover;
    background-position: center;
    height: 100%;
    width: 100%;

}

.poe1 {
    background-image: url("./assets/poe1.png");

}

.poe2 {
    background-image: url("./assets/poe2.png");
}

.poe3 {
    background-image: url("./assets/poe3.png");
}

.poe4 {
    background-image: url("./assets/poe2-alt.png");
}

.poe5 {
    background-image: url("./assets/poe-3alt.png");
}

.poe1>.caption {
    background: -webkit-linear-gradient(#28373B, #91A98F);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}




.poe2>.caption {
    background: -webkit-linear-gradient(#515850, #142927);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

.poe3>.caption {
    padding-top: 2rem;
    background: -webkit-linear-gradient(#14171a, #eee);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}




.caption {

    font-size: 50px;
    text-align: center;
    width: 100rem;
    margin: auto;
    padding-top: 30rem;
    color: #DADBB0;
    line-height: 70px;
    opacity: .8;
    display: none;


}


.section:hover .caption {
    animation: moveInLeft 1s ease-in;
    display: block;
}

/* PRELOADER */

#preloader {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: #2c3e50;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
    height: 100%;
    z-index: 99;
    /* makes sure it stays on top */
}

#status {
    width: 50px;
    height: 30px;
    position: fixed;
    left: 50%;
    /* centers the loading animation horizontally one the screen */
    top: 50%;
    /* centers the loading animation vertically one the screen */
    margin: -25px 0 0 -15px;
    /* is width and height divided by two */
}

.spinner {
    margin: 0px auto;
    width: 50px;
    height: 30px;
    text-align: center;
    font-size: 10px;
}

.spinner>div {
    background-color: #fff;
    height: 100%;
    width: 6px;
    display: inline-block;

    -webkit-animation: stretchdelay 1.2s infinite ease-in-out;
    animation: stretchdelay 1.2s infinite ease-in-out;
}

.spinner .rect2 {
    -webkit-animation-delay: -1.1s;
    animation-delay: -1.1s;
}

.spinner .rect3 {
    -webkit-animation-delay: -1.0s;
    animation-delay: -1.0s;
}

.spinner .rect4 {
    -webkit-animation-delay: -0.9s;
    animation-delay: -0.9s;
}

.spinner .rect5 {
    -webkit-animation-delay: -0.8s;
    animation-delay: -0.8s;
}

@-webkit-keyframes stretchdelay {

    0%,
    40%,
    100% {
        -webkit-transform: scaleY(0.4)
    }

    20% {
        -webkit-transform: scaleY(1.0)
    }
}

@keyframes stretchdelay {

    0%,
    40%,
    100% {
        transform: scaleY(0.4);
        -webkit-transform: scaleY(0.4);
    }

    20% {
        transform: scaleY(1.0);
        -webkit-transform: scaleY(1.0);
    }
}

/* Transition */
.fade-enter-active,
.fade-leave-active {
    transition: opacity 0.5s;
}

.fade-enter,
.fade-leave-to {
    opacity: 0;
}
</style>