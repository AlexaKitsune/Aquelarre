<template>

    <span id="container-pentagram">
        <div class="symbol-external-circle">
            <div class="symbol-internal-circle"></div>
            <div class="symbol-internal-circle-2"></div>
            <div class="symbol-internal-circle-3"></div>
            <div class="symbol-internal-circle-4"></div>
            <div id="symbol-pentagon">
                <div class="pentagon-side1"></div>
                <div class="pentagon-side2"></div>
                <div class="pentagon-side3"></div>
                <div class="pentagon-side4"></div>
                <div class="pentagon-side5"></div>
            </div>
            <div id="symbol-star">
                <div class="star-side1"></div>
                <div class="star-side2"></div>
                <div class="star-side3"></div>
                <div class="star-side4"></div>
                <div class="star-side5"></div>
            </div>
            <div id="symbol-imgs">
                <img class="imgs-1" src="@/assets/animal_pillars/silhouette_cat.png">
                <img class="imgs-2" src="@/assets/animal_pillars/silhouette_fox.png">
                <img class="imgs-3" src="@/assets/animal_pillars/silhouette_doe.png">
                <img class="imgs-4" src="@/assets/animal_pillars/silhouette_cow.png">
                <img class="imgs-5" src="@/assets/animal_pillars/silhouette_hyen.png">
            </div>
            <div id="symbol-shapes">
                <div class="symbol-shape1"><div class="symbol-shape_"></div></div>
                <div class="symbol-shape2"><div class="symbol-shape_"></div></div>
                <div class="symbol-shape3"><div class="symbol-shape_"></div></div>
                <div class="symbol-shape4"><div class="symbol-shape_"></div></div>
                <div class="symbol-shape5"><div class="symbol-shape_"></div></div>
            </div>
        </div>
    </span>

</template>

<script>
export default {
    name: 'AquelarrePentagram'
}
</script>

<style scoped>
#container-pentagram {
    /*border: 1px solid green;*/
    width: 20vw;
    height: 20vw;
}

/* Symbol */
.symbol-external-circle,
.symbol-internal-circle,
.symbol-internal-circle-2,
.symbol-internal-circle-3,
.symbol-internal-circle-4 {
    border-radius: 100vw;
}

.symbol-external-circle {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
}

.symbol-external-circle * {
    position: absolute;
}

.symbol-internal-circle {
    width: 86%;
    height: 86%;
}

.symbol-internal-circle-2 {
    width: 47%;
    height: 47%;
}

.symbol-internal-circle-3 {
    width: 20%;
    height: 20%;
}

.symbol-internal-circle-4 {
    width: 105%;
    height: 105%;
}

/* Pentagon */
#symbol-pentagon {
    margin-left: -1px;
    width: 38%;
    height: 38%;
    display: flex;
    align-items: flex-end;
    justify-content: center;
    border-radius: 100vw;
    position: absolute;
}

.pentagon-side1,
.pentagon-side2,
.pentagon-side3,
.pentagon-side4,
.pentagon-side5 {
    width: 73%;
    height: 50%;
    transform-origin: 50% 0;
}

.pentagon-side1 {
    transform: rotate(000deg);
}

.pentagon-side2 {
    transform: rotate(072deg);
}

.pentagon-side3 {
    transform: rotate(144deg);
}

.pentagon-side4 {
    transform: rotate(216deg);
}

.pentagon-side5 {
    transform: rotate(288deg);
}

/* Star */
#symbol-star {
    width: 31%;
    height: 31%;
    display: flex;
    align-items: flex-end;
    justify-content: center;
    border-radius: 100vw;
    position: absolute;
    transform: rotate(180deg);
}

.star-side1,
.star-side2,
.star-side3,
.star-side4,
.star-side5 {
    width: 309%;
    height: 50%;
    transform-origin: 50% 0;
}

.star-side1 {
    transform: rotate(000deg);
}

.star-side2 {
    transform: rotate(072deg);
}

.star-side3 {
    transform: rotate(144deg);
}

.star-side4 {
    transform: rotate(216deg);
}

.star-side5 {
    transform: rotate(288deg);
}

/* imgs */
#symbol-imgs {
    width: 100%;
    height: 100%;
    border-radius: 3vw;
    display: flex;
    align-items: flex-start;
    justify-content: center;
}

.imgs-1,
.imgs-2,
.imgs-3,
.imgs-4,
.imgs-5 {
    width: 15%;
    padding-bottom: 55%;
    margin-top: -18%;
    transform-origin: 50% 100%;
    /*filter: drop-shadow(5px 5px 5px red);*/
}

.imgs-1 {
    transform: rotate(000deg);
}

.imgs-2 {
    transform: rotate(072deg);
}

.imgs-3 {
    transform: rotate(144deg);
}

.imgs-4 {
    transform: rotate(216deg);
}

.imgs-5 {
    transform: rotate(288deg);
}

/* Shapes */
#symbol-shapes {
    position: absolute;
    width: 80%;
    height: 80%;
    display: flex;
    align-items: flex-end;
    justify-content: center;
}

.symbol-shape1,
.symbol-shape2,
.symbol-shape3,
.symbol-shape4,
.symbol-shape5 {
    height: 50%;
    width: 5%;
    display: flex;
    align-items: flex-end;
    justify-content: center;
    transform-origin: 50% 0;
}

.symbol-shape_ {
    width: 100%;
    height: 10%;
    border-radius: 100vw;
}

.symbol-shape1 {
    transform: rotate(000deg);
}

.symbol-shape2 {
    transform: rotate(072deg);
}

.symbol-shape3 {
    transform: rotate(144deg);
}

.symbol-shape4 {
    transform: rotate(216deg);
}

.symbol-shape5 {
    transform: rotate(288deg);
}

/* Colors */
.symbol-external-circle,
.symbol-internal-circle,
.symbol-internal-circle-2,
.symbol-internal-circle-3,
.symbol-internal-circle-4,
.symbol-shape_ {
    border: 3px solid orange;
    transition: all 0.5s;
}

.pentagon-side1,
.pentagon-side2,
.pentagon-side3,
.pentagon-side4,
.pentagon-side5,
.star-side1,
.star-side2,
.star-side3,
.star-side4,
.star-side5 {
    border-bottom: 3px solid orange;
    transition: all 0.5s;
}

/* Animations transition (pentagon, star, img, shapes) */
#symbol-pentagon,
#symbol-star,
#symbol-imgs,
#symbol-shapes {
    transition: transform 1s;
}

#container-pentagram:hover #symbol-pentagon,
#container-pentagram:hover #symbol-star,
#container-pentagram:hover #symbol-imgs,
#container-pentagram:hover #symbol-shapes {
    transition: transform 1s;
    cursor: pointer;
}

#container-pentagram:hover #symbol-pentagon {
    transform: rotate(180deg);
}

#container-pentagram:hover #symbol-star {
    transform: rotate(72deg);
}

#container-pentagram:hover #symbol-imgs {
    transform: rotate(108deg);
}

#container-pentagram:hover #symbol-shapes {
    transform: rotate(252deg);
}

#container-pentagram:hover .symbol-external-circle,
#container-pentagram:hover .symbol-internal-circle,
#container-pentagram:hover .symbol-internal-circle-2,
#container-pentagram:hover .symbol-internal-circle-3,
#container-pentagram:hover .symbol-internal-circle-4,
#container-pentagram:hover .symbol-shape_ {
    border: 3px solid #00fff0;
    box-shadow: 0 0 15px #00fff0, 0 0 12px #00fff0 inset;
    transition: all 0.3s;
}

#container-pentagram:hover .pentagon-side1,
#container-pentagram:hover .pentagon-side2,
#container-pentagram:hover .pentagon-side3,
#container-pentagram:hover .pentagon-side4,
#container-pentagram:hover .pentagon-side5,
#container-pentagram:hover .star-side1,
#container-pentagram:hover .star-side2,
#container-pentagram:hover .star-side3,
#container-pentagram:hover .star-side4,
#container-pentagram:hover .star-side5 {
    border-bottom: 3px solid #00fff0;
    box-shadow: 0px 10px 12px -10px #00fff0, 0 -10px 12px -10px #00fff0 inset;
    transition: all 0.3s;
}

/* Animation infinte */
/*.set-rotations-pentagon, .set-rotations-star, .set-rotations-imgs, .set-rotations-shapes{
    animation-name: rotates_ !important;
    animation-iteration-count: infinite;
    transition: all;
}
.set-rotations-star{
    animation-name: rotates_star !important;
    animation-iteration-count: infinite;
    transition: all;
}

.set-rotations-pentagon{ animation-duration: 1s; }
.set-rotations-star{ animation-duration: 2s; }
.set-rotations-imgs{ animation-duration: 3s; }
.set-rotations-shapes{ animation-duration: 4s; }

@keyframes rotates_star{
    form{ transform:rotate(0deg); }
    to{ transform:rotate(-35deg); }
}

@keyframes rotates_{
    form{ transform:rotate(0deg); }
    to{ transform:rotate(360deg); }
}*/
</style>