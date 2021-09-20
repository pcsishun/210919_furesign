<template>
  <div class="marketplace">
    <section>
      <h2>ตลาดสินค้าเฟอร์นิเจอร์และของตกแต่งบ้านออนไลน์</h2>
      <h1 style="margin-top: 0px; margin-bottom: 10px"><b>ค้นหาสินค้า</b>ผ่านคำและรูปภาพ</h1>
      <div class="search">
        <div class="upload-btn-wrapper">
          <h4 v-if="file !=''">Your file upload</h4>
          <p v-if="file !=''" >{{ this.file['name'] }}</p>
          <button v-if="file !=''" class="btn">Re-upload</button>
          <button v-if="file ===''" class="btn">Upload image</button>
          <input  type="file" id="file"  ref="file" v-on:change="handleFileUpload" >
        </div>
        <div class="serach-button">
          <button v-if="file !=''" v-on:click="submitFile">Serach</button>
        </div>
        {{ imageList }}
      </div>
    </section>
  </div>
</template>

<script>
import { Splide, SplideSlide } from '@splidejs/vue-splide';
import '@splidejs/splide/dist/css/themes/splide-default.min.css';
import axios from 'axios';
// import '../assets/js/cameraSet.js';

export default {
  name: 'Marketplace',
  el: "#app-cam",
  components: {
    Splide,
    SplideSlide,
  },
  data(){
    return {
      imageList: null,
      options: 
      {
        rewind : true,
        width  : 800,
        gap    : '1rem',
      },
      isCameraOpen: false,
      isPhotoTaken: false,
      isShotPhoto: false,
      isLoading: false,
      link: '#',
      file: "",

    }
  },
  mounted(){
    axios
    .get("http://localhost:5000/productSerach")
    .then(response => (this.imageList = response.data))
  },
    
    methods: {
      submitFile(){
        let formData = new FormData();
        formData.append('file', this.file); // append image file name as file in variable formData

        axios.post('http://localhost:5000/single-file', 
        formData,
          {
          headers: {'Content-Type': 'multipart/form-data'}
          }
        )
      },

      handleFileUpload(){
        this.file = this.$refs.file.files[0];
        console.log(this.file['name'])
      }

    }
}
</script>
  
<style scoped>
  .marketplace {
    font-family: 'Prompt', sans-serif;
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    align-content: stretch;
    justify-content: space-evenly;
  }

  .seacrh {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 20px;
    border-radius: 3px;
  }

  section {
    background-color: white;
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
    align-items: center;
    justify-content: center;
    padding-left: 3.5vw;
    padding-right: 3.5vw;
    margin: 1vw 1.5vw;
    border-radius: 20px;
    box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
    height: 70vh;
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

  input {
    font-family: 'Prompt', sans-serif;
    font-size: min(1.5vw, 15px);
    border-radius: 10px;
    padding: min(1vw, 5px) min(2vw,10px);
    width: 30vw;
  }

  #coverImg {
      width: min(80vw, 1000px);
      margin: 2vw;
  }

  button {
      background-color: rgb(169, 126, 109);
      color: white;
      font-size: min(1.5vw, 15px);
      font-family: 'Prompt', sans-serif;
      margin: 10px;
      padding: min(1vw, 5px) min(2vw,10px);
      border-radius: min(1vw, 15px);
  }

  .upload-btn-wrapper {
  position: relative;
  overflow: hidden;
  display: inline-block;
}

.btn {
  border: 2px solid gray;
  color: gray;
  background-color: white;
  padding: 8px 20px;
  border-radius: 8px;
  font-size: 20px;
  font-weight: bold;
}

.upload-btn-wrapper input[type=file] {
  font-size: 100px;
  position: absolute;
  left: 0;
  top: 0;
  opacity: 0;
}
</style>
