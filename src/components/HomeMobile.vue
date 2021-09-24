<template>
    <div class="homeDesktop">
        <section>
            <h2>ตลาดสินค้าเฟอร์นิเจอร์และของตกแต่งบ้านออนไลน์</h2>
            <h1><b>ค้นหาง่าย</b>ทั้งไอเดียและสินค้า</h1>
            <button @click="$router.push({ path: 'marketplace' })">ค้นหาสินค้า</button>
            <img id="coverImg" src="../assets/cover.gif" alt="app demo">
        </section>

        <section>
            <table>
                <tr>
                    <td style="height: -10px">
                        <h1 id="subH1"><b>Idea Community</b></h1>
                    </td>
                    <td>
                        <h1 id="subH1"><b>Online Shopping</b></h1>
                    </td>
                </tr>
                <tr>
                    <td>
                        <div class="subTopic">
                            <img src="../assets/idea.png">
                            <h2 id="subH2">แหล่งชุมชนออนไลน์ที่รวบรวมไอเดียการแต่งพื้นที่อาศัย</h2>
                        </div>
                    </td>
                    <td>
                        <div class="subTopic">
                            <img src="../assets/cart.png">
                            <h2 id="subH2">ตลาดสินค้าเฟอร์นิเจอร์และของตกแต่งบ้านที่ค้นหาได้ง่ายผ่านรูปภาพ</h2>
                        </div>
                    </td>
                </tr>
            </table>
        </section>

        <section>
            <h1 id="sliderH1">ทำไม? ต้องซื้อเฟอร์นิเจอร์ของตกแต่งผ่าน <b>Furesign</b></h1>
            <splide :options="options">
                <splide-slide>
                    <div class="slideContent">
                        <div class="topic2">
                            <img src="../assets/pic2-v6-crop.gif" alt="search by image" style="width: max(22vw, 180px); margin-right: 0px">
                            <article>
                                <h1 id="contentH1"><b>ค้นหาสินค้าได้ง่าย</b>ผ่านคำและรูปภาพ</h1>
                                <h2 style="text-align: left;">ช่วยคุณค้นหาสินค้าได้ง่ายผ่านรูปภาพ โดยระบบจะค้นหาสินค้าที่เหมือนหรือใกล้เคียงกับภาพต้นแบบมากที่สุด</h2>
                                <button id="buttonSlide" @click="$router.push({ path: 'marketplace' })">ทดลองใช้</button>
                            </article>
                        </div>
                    </div>
                </splide-slide>

                <splide-slide>
                    <div class="slideContent">
                        <div class="topic2">
                            <img src="../assets/pic3-V3.png" alt="idea community">
                            <article>
                                <h1 id="contentH1"><b>แหล่งรวบรวมไอเดีย</b>การตกแต่งพื้นที่</h1>
                                <h2 style="text-align: left">หาไอเดียการแต่งบ้านและพื้นที่ต่าง ๆ ได้ง่ายผ่านแหล่งชุมชนออนไลน์บน Furesign</h2>
                                <button id="buttonSlide" @click="$router.push({ path: 'marketplace' })">Community</button>
                            </article>
                        </div>
                    </div>
                </splide-slide>

                <splide-slide>
                    <div class="slideContent">
                        <div class="topic2">
                            <img src="../assets/pic4-V2.png" alt="idea recommendation">
                            <article>
                                <h1 id="contentH1"><b>แนะนำสินค้า</b>ที่ตรงตามไอเดียที่สนใจ</h1>
                                <h2 style="text-align: left;">สั่งซื้อสินค้าผ่านไอเดียที่คุณสนใจได้ง่ายผ่านระบบของ Furesign</h2>
                            </article>
                        </div>
                    </div>
                </splide-slide>
            </splide>
        </section>
    </div>
</template>

<script>

import '@splidejs/splide/dist/css/themes/splide-default.min.css';
import { Splide, SplideSlide } from '@splidejs/vue-splide';

export default {
    name: 'HomeMobile',
    components: {
        Splide,
        SplideSlide
    },
    data:() => {
        return {
        options: {
          rewind : true,
          width: '95vw',
          gap    : '1rem',
          // autoplay: true
      }
    }
  }
}
</script>

<style scoped>

.homeDesktop {
    font-family: 'Prompt', sans-serif;
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    align-content: center;
    justify-content: center;
    margin: 0px;
    padding: 0px;
}

.topic {
    display: flex;
    justify-content: center;
    align-items: center;
}

.subTopic {
    display: flex;
    justify-content: flex-start;
    align-content: center;
    align-items: center;
}

.subTopic img {
    margin-left: 0px;
    margin-right: max(1vw, 10px);
    border-radius: 0px;
    width: max(3.5vw, 22px);
    /* width: min(3.5vw, 60px); */
    height: 100%;
}

.topic img {
    margin-right: 1vw;
    border-radius: 0px;
    width: min(3.5vw, 60px);
    height: 100%;
}

.topic h1 {
    margin-top: 0px;
    margin-bottom: 0px;
}

.topic2 {
    width: 80vw;
    margin-bottom: 5vw;
    display: flex;
    justify-content: center;
    align-items: center;
}

.topic2 h2 {
    width: 35vw;
    font-size: max(1.5vw, 12px);
    margin-top: 0px;
}

.topic2 img {
    width: max(17vw, 130px);
    border-radius: 0px;
    margin-right: 3vw;
}

.slideContent {
    display: flex;   
    justify-content: center;
}

.slideContent h1 {
    font-size: min(2.85vw, 36px);
}


section {
    background-color: white;
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
    align-items: center;
    justify-content: center;
    margin-bottom: 1vh;
}

@media screen and (min-width: 1200px) {
  section {
    margin: 10px 3.5vw;
  }
}

h1 {
    font-weight: 400;
    font-size: max(3.15vw, 26px);
    /* font-size: min(3.15vw, 52px); */
    margin-top: 0px; 
    margin-bottom: 10px;
}

#subH1 {
    font-size: max(1.68vw, 15px);
    /* font-size: min(1.23vw, 28px); */
    text-align: left;
    margin-bottom: 0px;
}

#sliderH1 {
    font-size: max(2.6vw, 20px);
}

h2 {
    font-weight: 400;
    font-size: max(1.58vw, 13px);
    /* font-size: min(1.58vw, 26px);   */
    margin-bottom: 0px;
}

#subH2 {
    font-size: max(1.23vw, 12px);
    /* font-size: min(1.23vw, 20px); */
    text-align: left; 
    margin-top: 0px;
}

#contentH1 {
    margin-top: 0px; 
    font-size: max(2.4vw, 15px)
}

b {
    font-weight: 700;
    color: rgb(169, 126, 109);
}

img {
    border-radius: 20px;
}

#coverImg {
    width: min(80vw, 1000px);
    margin: 2vw;
}

button {
    background-color: rgb(169 127 109);
    border: none;
    color: white;
    font-size: max(1.4vw, 12px);
    /* font-size: min(1.4vw, 23.6px); */
    font-family: 'Prompt', sans-serif;
    padding-top: max(0.3vw, 2.5px); 
    padding-bottom: max(0.3vw, 2.5px);
    padding-left: max(1.75vw, 15px);
    padding-right: max(1.75vw, 15px);
    border-radius: 100px;
}

button:active {
    background-color: rgb(154 107 88);
}

#buttonSlide {
    margin-top: 2vh;
    padding-top: max(1vw, 7.5px); 
    padding-bottom: max(1vw, 7.5px);
    padding-left: max(2.5vw, 17.5px);
    padding-right: max(2.5vw, 17.5px);
}

table {
    margin-bottom: 1.5vh;
    table-layout: fixed;
    width: max(65vw, 350px);
}

@media screen and (max-width: 340px) {
table {
    width: max(65vw, 280px);
}
}

td {
    padding-left: max(1.5vw, 2px);
    padding-right: max(1.5vw, 2px);
}

article {
    display: flex;
    flex-direction: column;
    align-items: center;
}

</style>