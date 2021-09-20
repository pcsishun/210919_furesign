<template>
  <div class="marketplace">
    <section>
      <h2>ตลาดสินค้าเฟอร์นิเจอร์และของตกแต่งบ้านออนไลน์</h2>
      <h1 style="margin-top: 0px; margin-bottom: 10px"><b>ค้นหาสินค้า</b>ผ่านคำและรูปภาพ</h1>
      <div class="search">
        <input type="text" placeholder="Search..">
        <button> Upload image</button>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'Marketplace'
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
</style>
