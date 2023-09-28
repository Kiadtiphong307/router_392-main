<template>
  <div class="box_all">
    <div class="col" v-for="(item, index) in travelList" :key="index">
      <div class="card">
        <img :src="item.img" class="card-img-top" alt="Travel Destination">
        <div class="card-body">
          <h3 class="card-title">{{ item.name }}</h3>
          <p class="card-text">ราคาโต๊ะ: {{ item.price }} บาท</p>
          <h6 class="card-subtitle">*** จำกัด 5 คนต่อ 1 โต๊ะ ***</h6>
          <button class="btn btn-primary" @click="list_local_control(item.name, item.quantity)">จองโต๊ะ</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const travelList=ref([{
  name: 'ท่าช้าง คาเฟ่',
  price: 200,
  img: "https://media.discordapp.net/attachments/1153766321666932836/1153887348094943232/6.jpg?width=585&height=585",
  quantity: 0
}]);

const list_local_control = (name, quantity) => {
  console.log(`Reservation made for: ${name} with quantity: ${quantity}`);
}
</script>


<style scoped>
.card {
  width: 18rem;
  margin: 20px;
  border: 1px solid #ddd;
  border-radius: 10px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.card-img-top {
  height: 200px;
  object-fit: cover;
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
}

.card-body {
  padding: 20px;
}

.card-title {
  font-size: 1.5rem;
  margin-bottom: 10px;
}

.card-text {
  font-size: 1.2rem;
}

.card-subtitle {
  font-size: 1rem;
  color: #888;
  margin-top: 10px;
}

.btn-primary {
  background-color: #007BFF;
  border: none;
  border-radius: 5px;
  color: #fff;
}

.btn-primary:hover {
  background-color: #0056b3;
}

.box_all {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  margin: 30px auto;
}
</style>