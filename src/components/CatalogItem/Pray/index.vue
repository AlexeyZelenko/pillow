<template>
  <div >
    <div class="catalog-item--pray">
      <div class="catalog-item--info">
        <div class="catalog-item--info__title">Благодійний фонд</div>
        <div class="catalog-item--info__subtitle">Сила доброти</div>
        <div class="catalog-item--info__text">Ваша підтримка дуже важлива!</div>
        <div class="catalog-item--info__button">
          <div class="catalog-item--info__donate">Пожертвувати</div>
        </div>
      </div>
      <div>
        <picture>
          <source srcset="@/assets/images/pray.webp" type="image/webp" media="(min-width: 700px)">
          <source srcset="@/assets/images/pray_mob.webp" type="image/webp" media="(max-width: 699px)">
          <source srcset="@/assets/images/pray_mob.png" type="image/png" media="(max-width: 699px)">
          <img src="@/assets/images/pray.png" alt="pray">
        </picture>
      </div>
    </div>
    <div class="catalog-item--about">
      <h3 class="catalog-item--about__title">О фонде</h3>
      <p class="catalog-item--about__dsc">Фонд начал свою деятельность в 1994 году. Мы помогаем пожилым людям и инвалидам улучшить условия и качество их жизни, поддерживать здоровье, реабилитироваться после операций. Мы организовываем досуг, благотворительные мероприятия и различные активности, чтобы пожилые были счастливы и чувствовали себя комфортно.</p>
    </div>
    <div class="catalog-item--blocks">
      <div
          class="catalog-item--block"
          v-for="item in items"
          :key="item.id"
      >
          <div class="catalog-item--block__img">
            <img :src="item.src" alt="">
          </div>
          <div class="catalog-item--block__title">{{item.title}}</div>
          <div class="catalog-item--block__text">{{item.text}}</div>
      </div>
    </div>
     <div class="catalog-item--direction">
         <div class="catalog-item--direction__title">Наші направлення</div>
         <div class="catalog-item--direction__subtitle">приєднуйтесь</div>
        <div>
           <div
                   v-for="item in directions"
                   :key="item.id"
           >
              <Direction :direction="item" />
           </div>
        </div>
     </div>
  </div>
</template>

<script>
import Direction from './Direction/index.vue';
export default {
   components: { Direction },
   data() {
    return {
       items: [
        {
          id: 1,
          src: 'van',
          title: '200 т +',
          text: 'We are a leading firm in providing quality and value to our customers.'
        },
        {
          id: 2,
          src: 'people',
          title: '20000 сімей +',
          text: 'Each member of our team has at least 5 years of legal experience..'
        },
        {
          id: 3,
          src: 'arm',
          title: '60 волонтерів +',
          text: 'Our managers are always ready to answer your questions. You can call us during the weekends and at night.'
        }
      ],
       directions: [
          {
             id: 1,
             title: 'Гроші на пальне',
             text: 'Гроші на пальне\n' +
                     'We are a leading firm in providing quality and value to our customers. Each member of our team has at least 5 years of legal experience. We like what we do.'
          },
          {
             id: 2,
             title: 'Купівля будівлі для церкви',
             text: 'Гроші на пальне\n' +
                     'We are a leading firm in providing quality and value to our customers. Each member of our team has at least 5 years of legal experience. We like what we do.'
          },
          {
             id: 3,
             title: 'Допомога дітям переселенцям',
             text: 'Гроші на пальне\n' +
                     'We are a leading firm in providing quality and value to our customers. Each member of our team has at least 5 years of legal experience. We like what we do.'
          }
       ]
    }
  },
}
</script>

<style scoped lang="scss">
.catalog-item {
    display: flex;
    flex-direction: column;
    justify-content: center;

   &--pray {
    margin-top: -738px;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: flex-end;
   }

   &--info {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    &__title {
      color: rgb(255 255 255);
      font-size: 48px;
      font-family: 'PT Sans',Arial,sans-serif;
      line-height: 1.2;
      font-weight: 300;
      letter-spacing: 1px;
    }

    &__subtitle {
      color: rgb(255 255 255);
      font-size: 72px;
      font-family: 'Montserrat',Arial,sans-serif;
      line-height: 1.2;
      font-weight: 700;
      letter-spacing: 1px;
      background-position: center center;
      border-color: rgb(0 0 0 / 0%);
      border-style: solid;
    }

    &__text {
      color: rgb(255 255 255);
      font-size: 26px;
      font-family: 'PT Sans',Arial,sans-serif;
      line-height: 1.5;
      font-weight: 500;
      background-position: center center;
      border-color: rgb(0 0 0 / 0%);
      border-style: solid;
    }

    &__button {
      border-width: 2px;
      border-radius: 20px;
      background-color: rgb(255 229 80);
      background-position: center center;
      border-color: rgb(0 123 255);
      border-style: solid;
      transition: background-color 0.2s ease-in-out, color 0.2s ease-in-out, border-color 0.2s ease-in-out;
      box-shadow: 0px 0px 20px 0px rgb(196 196 196);
      margin: 20px;
      cursor: pointer;
    }

    &__donate {
      color: rgb(0 0 0);
      text-align: center;
      padding: 10px 20px;
      text-decoration: none;
      font-size: 20px;
      font-weight: 600;
    }
   }

   &--about {
    padding-top: 15px;
    padding-bottom: 60px;
    background-color: rgb(184 231 255);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    &__title {
      font-size: 42px;
      margin: 20px auto 40px;
      text-align: center;
      font-weight: 600;
      color: #111111;
    }

    &__dsc {
      font-family: Avenir, Helvetica, Arial, sans-serif;
      font-weight: 300;
      color: #6d6d6d;
      font-size: 22px;
      max-width: 960px;
      line-height: 1.5;
    }

   }

   &--blocks {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding-top: 15px;
      padding-bottom: 30px;
      background-color: rgb(255 244 184);

     @media (min-width: 980px) {
        flex-direction: row;
     }
   }

   &--block {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      width: 100%;
      max-width: 300px;
      padding: 10px 30px;


     @media (min-width: 980px) {
        width: 33%;
        justify-content: flex-start;
        height: 250px;
     }

     &__title {
        font-family: 'Montserrat', Arial, sans-serif;
        font-weight: 600;
        color: rgb(0 0 0);
        margin: 10px;
     }

     &__text {
        font-size: 16px;
        line-height: 1.55;
        font-family: 'Montserrat', Arial, sans-serif;
        font-weight: 300;
        color: rgb(0 0 0);
     }
  }

   &--direction {
      margin: 20px auto;

      &__title {
         margin-bottom: 40px;
         font-size: 42px;
         line-height: 1.23;
         font-family: 'Montserrat',Arial,sans-serif;
         font-weight: 600;
         color: rgb(0 0 0);
      }

      &__subtitle {
         font-size: 24px;
         line-height: 1.5;
         font-family: 'Montserrat',Arial,sans-serif;
         font-weight: 300;
         color: rgb(0 0 0);
      }
   }

}
</style>