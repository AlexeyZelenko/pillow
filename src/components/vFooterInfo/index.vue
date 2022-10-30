<template>
   <footer class="footer">
      <div class="footer--info">
         <div class="footer--info__title">Контакти</div>
         <div class="footer--info__block">
            <div class="footer--info__text">Наша адреса: м. Черкаси, вул. Добровольського 5</div>
            <div class="footer--info__text">Телефон: +380637118781</div>
            <div class="footer--info__text">Email: partner@kindness-power.org</div>
         </div>
         <div class="footer--info__icons">
            <div
                    v-for="icon in icons"
                    :key="icon.id"
            >
               <img :src="`/src/assets/images/icons/${icon.src}.svg`" alt="">
            </div>
            <div class="footer--info__icon"></div>
         </div>
         <div class="footer--info__email">Email us: partner@kindness-power.org</div>
      </div>
   </footer>
</template>

<script>
export default {
   data() {
      return {
         icons: [
            {
               id: 1,
               src: 'email'
            },
            {
               id: 2,
               src: 'facebook'
            },
            {
               id: 3,
               src: 'insta'
            },
            {
               id: 4,
               src: 'youtube'
            }
         ]
      }
   },
}
</script>

<style scoped lang="scss">
.footer {
   display: flex;
   flex-direction: column;
   margin-top: -700px;

   &--info {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      //margin-top: -500px;

      &__title {
         color: rgb(255 255 255);
         padding: 40px 20px;
         font-size: 52px;
         line-height: 1.23;
         font-family: 'Montserrat',Arial,sans-serif;
         font-weight: 600;
      }

      &__block {
         display: flex;
         justify-content: flex-start;
         flex-direction: column;
      }

      &__text {
         text-align: left;
         font-size: 20px;
         line-height: 1.55;
         font-family: 'Montserrat',Arial,sans-serif;
         font-weight: 300;
         color: white;
      }

      &__icons {
         display: flex;
         flex-direction: row;
         align-items: center;
         justify-content: space-between;
         width: 400px;
         margin: 60px auto;
      }

      &__email {
         margin-top: 50px;
         color: rgb(255 255 255);
         padding: 0 20px;
         font-size: 15px;
         line-height: 1.55;
         font-family: 'PT Sans',Arial,sans-serif;
         font-weight: 300;
      }
   }
}
</style>