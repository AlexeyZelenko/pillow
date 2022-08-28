<template>
  <div ref="el" class="catalog-item">
    <div v-if="pray">
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
            <source srcset="../assets/images/pray.webp" type="image/webp" media="(min-width: 700px)">
            <source srcset="../assets/images/pray_mob.webp" type="image/webp" media="(max-width: 699px)">
            <source srcset="../assets/images/pray_mob.png" type="image/png" media="(max-width: 699px)">
            <img src="../assets/images/pray.png" alt="pray">
          </picture>
        </div>
      </div>
      <div class="catalog-item--about">
        <h3 class="catalog-item--about__title">О фонде</h3>
        <p class="catalog-item--about__dsc">Фонд начал свою деятельность в 1994 году. Мы помогаем пожилым людям и инвалидам улучшить условия и качество их жизни, поддерживать здоровье, реабилитироваться после операций. Мы организовываем досуг, благотворительные мероприятия и различные активности, чтобы пожилые были счастливы и чувствовали себя комфортно.</p>
      </div>
    </div>
    <div
      class="sec-text"
    >
      <h3 class="sec-text__title">{{title}}</h3>
      <p class="sec-text__dsc">{{text}}</p>
    </div>
    <section
      ref="el"
      :class="isShown ? sectionClass : null"
    ></section>
  </div>
</template>

<script>
import { ref, computed, onMounted, onBeforeUnmount } from 'vue'
import useIntersectionObserver from '../composables/useIntersectionObserver'

export default {
  name: 'CatalogItem',
  props: {
    data: Object
  },
  setup (props) {
    const el = ref(null)
    const { observe, unobserve, isShown } = useIntersectionObserver()
    const title = computed(
      () => props.data.title
    )
    const pray = computed(
        () => props.data.pray
    )
    const text = computed(
      () => props.data.text
    )
    const sectionClass = computed(
      () => props.data.sectionClass
    )

    onMounted(() => {
      observe(el.value)
    })

    onBeforeUnmount(() => {
      unobserve(el.value)
    })
    return {
      title,
      text,
      sectionClass,
      isShown,
      el,
      pray
    }
  }
}
</script>

<style scoped lang="scss">
.catalog-item {
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
}
  body {margin: 0;padding: 0;font-family: sans-serif;color: #262626;}

  section {
    width: 100%;
    height: 100vh;
    box-sizing: border-box;
  }
  section.sec1 {
    background: url('../assets/images/причастие.jpg')  no-repeat center / cover;
    background-attachment: fixed;
  }
  section.sec2 {
    background: url('../assets/images/nightPrayer.jpg') no-repeat center / cover;
    background-attachment: fixed;
  }
  section.sec3 {
    background: url('../assets/images/song.jpg')no-repeat center / cover;
    background-attachment: fixed;
  }
  section.sec4 {
    background: url('../assets/images/fire.jpg')no-repeat center / cover;
    background-attachment: fixed;
  }
  section.sec5 {
    background: url('../assets/images/water.jpg')no-repeat center / cover;
    background-attachment: fixed;
  }
  section.sec6 {
    background: url('../assets/images/centreHelp.jpg')no-repeat center / cover;
    background-attachment: fixed;
  }
  section.sec7 {
    background: url('../assets/images/homegroup.jpg')no-repeat center / cover;
    background-attachment: fixed;
  }
  section.sec8 {
    background: url('../assets/images/help.jpg')no-repeat center / cover;
    background-attachment: fixed;
  }
  section.sec9 {
    background: url('../assets/images/centreHelp.jpg')no-repeat center / cover;
    background-attachment: fixed;
  }
  .sec-text {
    padding: 1.5% 8%;
    height: auto;
  }
  .sec-text__title {
    margin: 0;
    padding: 0;
    font-size: 2em;
  }
  .sec-text__dsc {
    font-size: 1em;
  }
</style>
