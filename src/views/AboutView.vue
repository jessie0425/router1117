<template>
  <div class="about">
    <h1>This is an about page {{userId}}</h1>
    <p>測試1119</p>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>

<script>
import liff from '@line/liff';

export default {
  name: 'about',
  data() {
    return {
      userId: ''
    };
  },
  mounted(){
    liff
      .init({
        liffId: "2006570218-5mxGdm4R", // Use own liffId
      })
      .then(() => {
          console.log('串接成功')
          liff.getProfile()
              .then((res) => {
                this.userId = res.userId
              })
      })
  },
};
</script>

