<template>
    <div class="homeDesktop">
        <section>
            <h2 style="margin-bottom: 0px;">ตลาดสินค้าเฟอร์นิเจอร์และของตกแต่งบ้านออนไลน์</h2>
            <h1 style="margin-top: 0px; margin-bottom: 10px"><b>ค้นหาง่าย</b>ทั้งไอเดียและสินค้า</h1>
            <button @click="$router.push({ path: 'marketplace' })">ค้นหาสินค้า</button>
            <img id="coverImg" src="../assets/cover.gif" alt="app demo">
        </section>

        <section>
            <table>
                <tr>
                    <td>
                        <div class="topic">
                            <img src="../assets/online-community.png">
                            <h1><b>Idea Community</b></h1>
                        </div>
                            <h2>แหล่งชุมชนออนไลน์ที่รวบรวมไอเดียการแต่งพื้นที่อาศัย</h2>
                    </td>
                    <td>
                        <div class="topic">
                            <img src="../assets/shopping-cart.png">
                            <h1><b>Online Shopping</b></h1>
                        </div>
                        <h2>ตลาดสินค้าเฟอร์นิเจอร์และของตกแต่งบ้านที่ค้นหาได้ง่ายผ่านรูปภาพ</h2>
                    </td>
                </tr>
            </table>
        </section>

        <section>
            <h1>ทำไม? ต้องซื้อเฟอร์นิเจอร์ของตกแต่งผ่าน <b>Furesign</b></h1>
            <splide :options="options">
                <splide-slide>
                    <div class="slideContent">
                        <h1 style="margin-top: 0px"><b>ค้นหาสินค้าได้ง่าย</b>ผ่านคำและรูปภาพ</h1>
                        <div class="topic2">
                            <img src="../assets/Pic2-V4_crop.gif" alt="search by image" style="width: 18vw; margin-right: 0px">
                            <h2 style="text-align:center">ช่วยคุณค้นหาสินค้าได้ง่ายผ่านรูปภาพ โดยระบบจะค้นหาสินค้าที่เหมือนหรือใกล้เคียงกับภาพต้นแบบมากที่สุด</h2>
                        </div>
                    </div>
                </splide-slide>

                <splide-slide>
                    <div class="slideContent">
                        <h1 style="margin-top: 0px"><b>แหล่งรวบรวมไอเดีย</b>การตกแต่งพื้นที่</h1>
                        <div class="topic2">
                            <img src="../assets/pic3-V3.png" alt="idea community">
                            <h2 style="text-align:center">หาไอเดียการแต่งบ้านและพื้นที่ต่าง ๆ ได้ง่ายผ่านแหล่งชุมชนออนไลน์บน Furesign</h2>
                        </div>
                    </div>
                </splide-slide>

                <splide-slide>
                    <div class="slideContent">
                        <h1 style="margin-top: 0px"><b>แนะนำสินค้า</b>ที่ตรงตามไอเดียที่สนใจ</h1>
                        <div class="topic2">
                            <img src="../assets/pic4-V2.png" alt="idea recommendation">
                            <h2 style="text-align:center;">สั่งซื้อสินค้าผ่านไอเดียที่คุณสนใจได้ง่ายผ่านระบบของ Furesign</h2>
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
          width: '80vw',
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
    align-content: stretch;
    justify-content: space-evenly;
}

.topic {
    display: flex;
    justify-content: center;
    align-items: center;
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
    width: 60vw;
    margin-bottom: 5vw;
    display: flex;
    justify-content: center;
    align-items: center;
}

.topic2 h2 {
    width: 35vw;
    font-size: min(2.5vw, 30px);
}

.topic2 img {
    width: min(13vw, 270px);
    border-radius: 0px;
    margin-right: 3vw;
}

.slideContent {
    display: flex;
    flex-direction: column;
    align-items: center;
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
    padding-left: 3.5vw;
    padding-right: 3.5vw;
    margin: 1vw 1.5vw;
    border-radius: 20px;
    box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
}

@media screen and (min-width: 1200px) {
  section {
    margin: 10px 3.5vw;
  }
}

h1 {
    font-weight: 400;
    font-size: min(3vw, 45px);
}

h2 {
    font-weight: 400;
    font-size: min(2.5vw, 36px);
}

b {
    font-weight: 500;
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
    background-color: rgb(169, 126, 109);
    color: white;
    font-size: min(2.5vw, 36px);
    font-family: 'Prompt', sans-serif;
    padding: min(1vw, 5px) min(2vw,10px);
    border-radius: min(1vw, 15px);
}

</style>