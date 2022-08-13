<template>
    <section>

        <div id="popup-container">
            <div id="popup-showmenu" v-on:click="showMenu"><span id="menu-flecha">^</span>Menú</div>
            <div id="popup-closebutton" v-on:click="hidePopUp">+</div>
            <main>
                <aside id="popup-menu">
                    <p id="btn-misionvision" v-on:click="setArticle('misionvision')">Misión y visión</p>
                    <p id="btn-futuromejor" v-on:click="setArticle('futuromejor')">¿Cómo crearemos un futuro mejor?</p>
                    <p id="btn-quienessomos" v-on:click="setArticle('quienessomos')">¿Quienes somos?</p>
                    <p id="btn-comentarios" v-on:click="setArticle('comentarios')">Comentarios</p>
                </aside>
                <article>

                    <!--Mision y Visión-->
                    <div id="ARTICLE-misionvision">
                        <h1 class="article-title">Misión  y visión</h1>
                        <p class="article-paragraph">En El Aquelarre, buscamos crear un mundo mejor con base en el apoyo mutuo y orientación.</p>
                        <p>Crearemos un impacto positivo en cada miembro del Aquelarre, así como en su calidad de vida.</p>
                        <p><br></p>
                        <h1 class="article-title">Visión</h1>
                        <p>El objetivo del Aquelarre es crear un futuro mejor, para los integrantes del mismo y las personas que nos rodean.</p>
                    </div>

                    <!--Valores-->
                    <div id="ARTICLE-futuromejor">
                        <h1 class="article-title">¿Cómo crearemos un futuro mejor?</h1>
                        <h2 class="article-subtitle">Metas a Corto Plazo</h2>
                         <p>Crearemos una comunidad diversa con personas aptas y comprometidas por una mejora en común.<br></p>
                        <h2 class="article-subtitle">Metas a Mediano Plazo</h2>
                         <p>Llevaremos a cabo eventos mensuales o semestrales en los cuales haremos entregas de membresías y reconocimientos, intercambiaremos conocimientos y consolidaremos nuevas metas.<br></p>
                        <h2 class="article-subtitle">A futuro</h2>
                         <p>Tras haber alcanzado la estabilidad, cada integrante apoyará al anterior a dar sus pasos, y esto hará que empecemos a tener un impacto en la comunidad.<br></p>
                    </div>

                    <!--Quienes somos-->
                    <div id="ARTICLE-quienessomos">
                        <h1 class="article-title">¿Quienes somos?</h1>
                        <p>🦌🐱🐄🦊🐆</p>
                        <h2 class="article-subtitle">¿Cómo hago para formar parte de esto?</h2>
                         <p>Habla con la persona que te facilitó la información, ella te canalizará con nuestros <i>Sondeadores de Aptitud</i>, los cuales dictaminarán si tus valores se alínean con los de La Comunidad.</p>
                         <p>Tras una breve entrevista, tu proceso de inscripción estará casi completo. Se te proporcionarán unas metas personales sencillas, y si las cumples, ¡Felicidades, eres parte de La Comunidad!</p>
                    </div>
                    
                    <!--Comentarios-->
                    <div id="ARTICLE-comentarios">
                        <iframe src="/comment.html" id="iframecomments"></iframe>
                    </div>

                </article>
            </main>
        </div>

    </section>
</template>

<script>
export default {
    name: 'AquelarrePopUp',

    methods:{
        hidePopUp(){
            console.log("close");
            document.getElementById('popup-container').className = "popup-disappear";
            setTimeout(function(){
                document.getElementById('popup-MAIN').style.display = "none";
            },1000);
        },

        setArticle(clicked){
            let botones = ['misionvision', 'futuromejor', 'quienessomos', 'comentarios'];
            for(let boton of botones){
                document.getElementById(`btn-${boton}`).style.color = "white";
                document.getElementById(`btn-${boton}`).style.textShadow = "";
                document.getElementById(`btn-${boton}`).classList.remove('menu-selected');
                document.getElementById(`ARTICLE-${boton}`).style.display = "none";
                if(boton == 'comentarios'){ this.getCommentsUrl(); }
            }
            document.getElementById(`btn-${clicked}`).style.color = "#00fff0";
            document.getElementById(`btn-${clicked}`).style.textShadow = "0px 0px 15px #00fff0";
            document.getElementById(`btn-${clicked}`).classList.add('menu-selected');
            document.getElementById(`ARTICLE-${clicked}`).style.display = "flex";

            //Poner un match query para ocultar el menu solo en movil:
            var x = window.matchMedia("all and (max-width: 780px)");
            if (x.matches) {
                document.getElementById('popup-menu').style.transform = "scaleY(0)";
                document.getElementById('popup-showmenu').style.color = "white";
                document.getElementById('menu-flecha').style.borderColor = "white";
                document.getElementById('menu-flecha').style.boxShadow = "";
                document.getElementById('menu-flecha').style.transform = "rotate(180deg)";
            }
        },

        showMenu(){
            document.getElementById('popup-menu').style.transform = "scaleY(1)";
            document.getElementById('popup-showmenu').style.color = "#00fff0";
            document.getElementById('menu-flecha').style.borderColor = "#00fff0";
            document.getElementById('menu-flecha').style.boxShadow = "0px 0px 10px #00fff0";
            document.getElementById('menu-flecha').style.transform = "rotate(0deg)";
        },

        getCommentsUrl(){
            document.getElementById('iframecomments').src = `${window.location.href}/comment.html`;
        }

    },

    mounted(){
        this.setArticle('misionvision');
        this.getCommentsUrl();
    }

}
</script>

<style scoped>
section{
    width: 100%;
    height: 100vh;
    z-index: 1;
    position: fixed;
    display: flex;
    align-items: center;
    justify-content: center;
}

#popup-container{
    width: 80vw;
    height: 80vh;
    border-radius: 2vw;
    background-color: rgba(0,0,0, 40%);
    backdrop-filter: blur(5px);
    display: flex;
    align-items: center;
    justify-content: center;
}

#popup-showmenu{
    display: none;
}

#popup-closebutton{
    color: white;
    position: absolute;
    right: 1.1vw;
    top: 1.1vw;
    font-size: 2vw;
    border: 1px solid white;
    width: 2vw;
    height: 2vw;
    border-radius: 100vw;
    display: flex;
    align-items: center;
    justify-content: center;
    transform: rotate(45deg);
    transition: all 0.2s;
}
#popup-closebutton:hover{
    transition: all 0.1s;
    cursor: pointer;
    color: #00fff0;
    border: 1px solid #00fff0;
    transform: rotate(-45deg);
    box-shadow: 0px 0px 10px #00fff0;
}

.popup-appear{
    animation-name: popup-appear_ !important;
    animation-duration: 1s;
    animation-fill-mode: forwards;
}

.popup-disappear{
    animation-name: popup-disappear_ !important;
    animation-duration: 1s;
    animation-fill-mode: forwards;
}

@keyframes popup-appear_{
    0%{
        transform: scaleX(0) scaleY(0);
    }
    30%{
        transform: scaleX(1) scaleY(0.1);
    }
    100%{
        transform: scaleX(1) scaleY(1);
    }
}

@keyframes popup-disappear_{
    0%{
        transform: scaleX(1) scaleY(1);
    }
    30%{
        transform: scaleX(1) scaleY(0.1);
    }
    100%{
        transform: scaleX(0) scaleY(0);
    }
}

main{
    width: 95%;
    height: 80%;
    display: flex;
    position: relative;
}

aside{
    width: 22ch;
    height: 100%;
    padding: 0 1vw 0 1vw;
    border-right: 1px solid gray;
}

aside p{
    color: white;
    font-family: 'Plus Jakarta Sans', sans-serif;
    transition: all 0.2s;
    width: 100%;
}
aside p:hover{
    cursor: pointer;
    color: orange !important;
    transform: scale(1.1);
    transition: all 0.2s;
}

.menu-selected:hover{
    color: #00fff0 !important;
}

article{
    float: left;
    width: 100%;
    color: white;
    padding: 1ch;
    font-family: 'Plus Jakarta Sans', sans-serif;
}

/* articles */
#ARTICLE-misionvision, #ARTICLE-futuromejor, #ARTICLE-comentarios, #ARTICLE-quienessomos{
    width: 100%;
    height: 100%;
    overflow: auto;
    display: flex;
    flex-direction: column;
}

iframe{
    height: fit-content;
    width: 100%;
    min-height: 100%;
    overflow-x: hidden !important;
    overflow-y: hidden;
    background-color: transparent;
    border: none;
    border-radius: 0.6vw !important;
}

.article-title{
    font-family: 'Bebas Neue', cursive;
    color: #00fff0;
    font-size: 4ch;
    margin-bottom: 0;
    margin-top: 0;
}

.article-subtitle{
    font-family: 'Bebas Neue', cursive;
    font-size: 2.5ch;
    margin-bottom: -1ch;
}

/*************************************************************************
 * RESPONSIVE
 *************************************************************************/
@media all and (max-width:780px){

    #popup-container{
        width: 90vw;
        height: 90vh;
    }

    #popup-showmenu{
        display: flex;
        align-items: center;
        position: absolute;
        left: 3vw;
        top: 3vw;
        color: white;
        font-family: 'Plus Jakarta Sans', sans-serif;
    }
    #popup-showmenu span{
        border: 1px solid white;
        font-size: 6vw;
        width: 6vw;
        height: 4.5vw;
        border-radius: 100vw;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 140%;
        line-height: 0px;
        padding-top: 1.5vw;
        margin-right: 2vw;
        transform: rotate(180deg);
        transition: all 0.2s !important;
    }
    #popup-showmenu:hover{
        cursor: pointer;
        color:#00fff0 !important;
    }
    #popup-showmenu:hover span{
        border: 1px solid #00fff0 !important;
        box-shadow: 0px 0px 10px #00fff0 !important;
    }

    #popup-closebutton{
        right: 3vw;
        top: 3vw;
        font-size: 6vw;
        width: 6vw;
        height: 6vw;
    }

    main{
        display: flex !important;
        justify-content: center;
    }
    
    aside{
        width: fit-content;
        max-width: 95vw;
        position: absolute;
        height: fit-content;
        top: 0vw;
        left: 2vw;
        background-color: rgba(0,0,0,0.5);
        backdrop-filter: blur(5px);
        border: none;
        padding: 0 3vw 0 3vw;
        line-height: 4vh;
    }
    #popup-menu{
        transform: scale(0);
        transition: all 0.2s;
        transform-origin: 0% 0%;
    }

    article{
        width: 90%;
    }

}

</style>