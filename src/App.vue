<script setup>
import { ref, watch } from 'vue'

</script>
<template>
 
    <header class="d-flex flex-wrap justify-content-center py-3 mb-4 border-bottom" style="background-color: rgb(20, 20, 20);">
      <a href="/" class="d-flex align-items-center mb-3 mb-md-0 me-md-auto link-body-emphasis text-decoration-none">
        <svg class="bi me-2" width="40" height="60"><use xlink:href="#bootstrap"></use></svg>
        <span class="fs-3" style="color: rgb(255, 255, 255);">ระบบเรียกเก็บค่าเหล้าเรียน</span>
      </a>
    </header>

    <div class="concard">
      <div class="card">
        <div class="card-body">
          <div v-if="selectedOption === '0' " class="ifimg" style="max-width: 600px; max-height: 222px; margin: auto; margin-bottom: 1%; border-radius: 20px;">
              <img src="/src/assets/bimbim.png" alt="bimbim" style="border-radius: 20px;">
          </div>
          <div v-if="selectedOption > 0 " class="ifimg1" style="max-width: 222px; max-height: 222px; margin: auto;">
            <div class="prompttext" style="color: rgb(9, 62, 104); font-size: 16; font-weight: bolder;">
              PromptPay Qrcode
            </div> 
            <img :src="selectedImage" class="card-img-top" alt="bimbim">
          </div>
          <div class="textcon"><br>
          <h5 class="card-title">{{ name }}</h5>
          <h6 class="card-subtitle mb-2 text-body-secondary">{{ description }}</h6><br>
        </div>
        <div class="selectcon">
          <select class="form-select" v-model="selectedOption" aria-label="Default select example" style="margin-bottom: -2%;">
            <option value="0">ระบุชื่อของคุณ</option>
            <option value="1">แคป</option>
            <option value="2">เบนซ์</option>
            <option value="3">บิ๋ม56</option>
            <option value="4">หญิง</option>
            <option value="5">ภูมิ</option>
            <option value="6">บูม</option>
            <option value="7">ซอสุดหล่อ</option>
            <option value="8">ภูหล่อสุด</option>
            <option value="9">บอสหล่อเกิ้น</option>
            <option value="10">ไอติม56</option>
          </select><br>
        </div>
          
        </div>
      </div>
    </div>

    <div class="concard2">
      <div class="card2">
         <div class="manualtextbox">
          (19 กันยายน 2565 ณ ร้าน ฯลฯ) <br>
          เลือกชื่อของตนเอง <br> 
          QrCode และ รายละเอียดต่าง ๆ จะแสดง<br> 
          ถ่ายภาพหน้าจอ และ ใช้Applicationของธนาคาร <br>
          เพื่อชำระเงิน
           

         </div>
      </div>
    </div>
  <br>
    <footer>
      Created By Thonthus (Sorsudlor)
    </footer>
</template>

<script>
export default {
  data() {
    return {
      selectedOption: '0',
      name: 'โปรดระบุชื่อ',
      description: '',
    };
  },

  computed: {
    selectedImage() {
      switch (this.selectedOption) {
        case '0':
          this.name = 'โปรดระบุชื่อ';
          this.description = '0';
          return '/src/assets/bimbim.png';
        case '1':
          this.name = 'แคป';
          this.description = 'เหล้า + mixer 156 บาท';
          return 'https://promptpay.io/0648432286/156.png';
        case '2':
          this.name = 'เบนซ์';
          this.description = 'เหล้า + mixer 156 บาท';
          return 'https://promptpay.io/0648432286/156.png';
        case '3':
          this.name = 'บิ๋ม56';
          this.description = 'เหล้า + mixer 156 บาท';
          return 'https://promptpay.io/0648432286/156.png';
        case '4':
          this.name = 'หญิง';
          this.description = 'โค้ก 1 ขวด 65 บาท';
          return 'https://promptpay.io/0648432286/171.png';
        case '5':
          this.name = 'ภูมิ';
          this.description = 'เหล้า + mixer + French fries 171 บาท';
          return 'https://promptpay.io/0648432286/65.png';
        case '6':
          this.name = 'บูม';
          this.description = 'เหล้า + mixer + French fries 171 บาท';
          return 'https://promptpay.io/0648432286/65.png';
        case '7':
          this.name = 'ซอสุดหล่อ';
          this.description = 'เหล้า + mixer + French fries 171 บาท';
          return 'https://promptpay.io/0648432286/65.png';
        case '8':
          this.name = 'ภูหล่อสุด';
          this.description = 'เหล้า + mixer + French fries 171 บาท';
          return 'https://promptpay.io/0648432286/65.png';
        case '9':
          this.name = 'บอสหล่อเกิ้น';
          this.description = 'เหล้า + mixer + French fries 171 บาท';
          return 'https://promptpay.io/0648432286/65.png';
        case '10':
          this.name = 'ไอติม56';
          this.description = 'เหล้า + mixer + French fries 171 บาท';
          return 'https://promptpay.io/0648432286/65.png';
        default:
          this.name = 'ยังไม่เลือกชื่อ';
          this.description = '';
          return '/src/assets/bimbim.png';
      }
    },
  },
  watch: {
    selectedOption(newVal) {
      if (newVal === '0') {
        this.name = 'โปรดระบุชื่อ';
        this.description = '';
      }
    },
  },
};
</script>


<style scoped>

</style>
