<template>
  <header-bar></header-bar>
  <div  style="display: flex; justify-content: center; align-items: center; flex-direction: column;">
    <input type="file" @change="handleFileUpload">
    <img :src="originalImageUrl" v-if="originalImageUrl" alt="Uploaded Image">
    <button @click="uploadImage">上传图片</button>
    <p>预测结果:{{prediction}}</p>

<!--    <div >-->
<!--      <div >-->
<!--        <img :src="'data:image;base64,'+image">-->
<!--      </div>-->
<!--    </div>-->
  </div>
  <footer-bar></footer-bar>
</template>

<script >
import axios from "axios";
import HeaderBar from "@/components/HeaderBar.vue";
import FooterBar from "@/components/FooterPage.vue";

export default {
  components: {FooterBar, HeaderBar},
  data() {
    return {
      // image:'',
      file: null,
      originalImageUrl:null,
      prediction:""
    };
  },
  mounted() {
    // this.gain();
  },
  methods: {
    handleFileUpload(event) {
      this.file = event.target.files[0];
      this.originalImageUrl =URL.createObjectURL(this.file);
    },
    uploadImage() {
      let formData = new FormData();
      formData.append('image', this.file);

      axios.post('http://127.0.0.1:9200/predict', formData)
          .then(response => {
            console.log(response.data);
            // 更新识别结果
            this.prediction = response.data;
            console.log(this.prediction);
            // Handle response
          })
          .catch(error => {
            console.error('Error uploading image: ', error);
          });
    },
    // gain(){
    //   axios.get('http://localhost:8081/file/images').then((res)=>{
    //     console.log(res)
    //     this.image = res.data.data[0];
    //     // this.$message.success('图片获取成功');
    //     console.log('图片获取成功');
    //   }).catch(()=>{
    //     // this.$message.error('图片获取失败');
    //     console.log('图片获取失败');
    //   })
    // },
  }
};
</script>