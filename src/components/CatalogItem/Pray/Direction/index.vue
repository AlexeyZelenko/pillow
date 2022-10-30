<template>
   <div class="direction">
      <div v-if="direction" class="direction--block1">
         <div class="direction--block1__title">{{direction.title}}</div>
         <div class="direction--block1__text">{{direction.text}}</div>
         <div class="direction--block1__button">
            <div class="direction--block1__button-text">Детальніше</div>
         </div>
      </div>
      <div class="direction--block2">
         <picture>
            <source :srcset="`src/assets/images/direction/${direction.id}.webp`" type="image/webp">
            <source :srcset="`src/assets/images/direction/${direction.id}.png`" type="image/png">
            <img :src="`src/assets/images/direction/${direction.id}.png`" type="image/png" alt="direction">
         </picture>
      </div>
   </div>
</template>

<script>
export default {
   props: {
      direction: {
         type: Object,
         required: true
      },
   },
}
</script>

<style scoped lang="scss">
.direction {
   display: flex;
   flex-direction: column;
   justify-content: center;
   align-items: center;
   padding: 20px;

   @media (min-width: 980px) {
      flex-direction: row;
      padding: 50px;
   }

   &--block1 {
      width: 100%;
      display: flex;
      flex-direction: column;
      justify-content: space-evenly;
      align-items: flex-start;
      min-height: 400px;

      @media (min-width: 980px) {
         width: 50%;
         max-width: 460px;
      }

      &__title {
         font-size: 26px;
         line-height: 1.23;
         font-family: 'Montserrat',Arial,sans-serif;
         font-weight: 600;
         color: rgb(0 0 0);
      }

      &__text {
         font-size: 18px;
         line-height: 1.55;
         font-family: 'Montserrat',Arial,sans-serif;
         font-weight: 300;
         color: rgb(0 0 0);
         text-align: left;
      }

      &__button {
         color: rgb(1 91 187);
         border: 2px solid rgb(1 91 187);
         background-color: rgb(254 213 0);
         border-radius: 30px;
         -moz-border-radius: 30px;
         -webkit-border-radius: 30px;
         box-shadow: 0 0 15px 0 rgba(0, 0, 0, 0.3);
         cursor: pointer;

         &:hover {
            transition: background-color 0.2s ease-in-out, color 0.2s ease-in-out, border-color 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
         }

         &-text {
            font-size: 14px;
            font-weight: 700;
            color: rgb(1 91 187);
            padding: 10px 20px;
         }
      }
   }

   &--block2 {
      width: 100%;
      display: flex;
      flex-direction: column;
      justify-content: space-around;
      align-items: center;
      min-height: 400px;

      @media (min-width: 980px) {
         width: 50%;
      }
   }
}
</style>