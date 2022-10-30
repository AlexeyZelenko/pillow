<template>
  <div class="navbar">
    <div class="navbar--logo">
      <a href="#home">
        <img style="height: 80px" src="./assets/images/logo.png" alt="">
      </a>
    </div>
    <div class="navbar--menu">
      <a href="#home">Home</a>
      <a href="#news">News</a>
      <a href="#contact">Contact</a>
    </div>
    <div class="navbar--icons">
      <div>
        <img src="./assets/images/facebook.svg" alt="facebook">
      </div>
      <div>
        <img src="./assets/images/telegram.svg" alt="telegram">
      </div>
    </div>
    <div class="navbar--button">
      <div class="navbar--button__text">Пожертвувати</div>
    </div>
    <div class="navbar--translate">
      <div class="navbar--translate__text">En</div>
      <div class="navbar--translate__text">Укр</div>
    </div>
  </div>
  <!--  Фото с описанием-->
  <vCatalogItem
      v-for="(product, i) in sections"
      :key="product.title"
      :index="i"
      :data="product"
  />
   <vFooterInfo />

</template>

<script>
import { defineAsyncComponent } from 'vue'

const vCatalogItem = defineAsyncComponent(() => import('./components/CatalogItem/index.vue'))
const vFooterInfo = defineAsyncComponent(() => import('./components/vFooterInfo/index.vue'))

export default {
  name: 'AboutUs',
  components: {
    vCatalogItem,
     vFooterInfo
  },
  data: () => ({
    sections: [
      {
        // title: 'Домашні церкви',
        // text: `Ми називаємо їх дуже ніжно: "Домашки". На "домашках" ми вивчаємо Слово Боже, молимось один за одного, п'єм чай. \n
        //   Вперше поняття «домашньої церкви» зустрічається в посланнях апостола Павла (1 Кор. 16:19; Рим. 16: 4)`,
        sectionClass: 'sec7',
        seen: true
      },
      {
        title: 'Новини',
        text: `Мы регулярно проводим различные мероприятия и благотворительные программы`,
        sectionClass: 'sec8',
        seen: true,
        pray: true
      },
      {
        title: 'Команда',
        text: 'Если вы хотите присоединиться к нашей команде, свяжитесь с нами по почте hello@company.com',
        sectionClass: 'sec9',
        seen: true,
        footer: true
      }
    ],
    TextBible: {}
  }),
  async mounted () {
    const response = await fetch('https://blv-vue3-tp.firebaseio.com/bible.json')
    const data = await response.json()

    const arrayVerse = Object.keys(data).map(key => {
      return { ...data[key], id: key }
    })

    this.TextBible = arrayVerse[Math.floor(Math.random() * arrayVerse.length)]
  }
}
</script>

<style scoped lang="scss">
.navbar {
  overflow: hidden;
  background-color: rgb(255 255 255);
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.30);
  position: fixed;
  top: 0;
  width: 100%;
  height: 80px;
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  align-content: center;

  &--menu {
      display: flex;
      flex-direction: row;
      align-items: center;
      justify-content: center;
   }

  &--icons {
      display: flex;
      flex-direction: row;
      align-items: center;
      width: 70px;
      justify-content: space-between;
      margin-left: 20px;
      cursor: pointer;
  }

  &--button {
    color: rgb(0 0 0);
    border: 2px solid rgb(0 87 186);
    background-color: rgb(255 255 255);
    border-radius: 20px;
    margin: 0 20px;
    cursor: pointer;

    &__text {
      color: black;
      text-align: center;
      padding: 5px 16px;
      text-decoration: none;
      font-size: 17px;
      font-weight: 600;
    }
  }

  &--translate {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    margin: 0 10px;
    cursor: pointer;

    &__text {
      color: #d2d2d2;
      text-align: center;
      padding: 5px 16px;
      text-decoration: none;
      font-size: 17px;
      font-weight: 600;
    }
  }
}

.navbar a {
  float: left;
  display: block;
  color: black;
  text-align: left;
  padding: 5px 16px;
  text-decoration: none;
  font-size: 17px;
  font-weight: 600;
}

.navbar a:hover {
  background: #ddd;
  color: black;
  border-radius: 20px;
}

.main {
  padding: 16px;
  margin-top: 30px;
  height: 1500px; /* Used in this example to enable scrolling */
}

.fullscreen-bg {
  overflow: hidden;
  position: relative;
  height: 100%;
  width: 100%;
  padding-top:45%;
}

.fullscreen-bg__video {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
}
.overlay {
  background: rgba(0,0,0,0.6);
  position: absolute;
  top:0;
  left:0;
  width: 100%;
  height: 100%;
  z-index: 4;
  text-align:center;
}
.overlay h1 {
  text-align:center;
  color:#fff;
  font-size: 45px;
  margin:10% 10%;
  text-shadow: 0 0 10px black;
}
@media (max-width: 767px) {
  .fullscreen-bg {
    background: url('./assets/images/earth.jpg') center center / cover no-repeat;
    padding-top: 70%;
  }
  .fullscreen-bg__video {
    display: none;
  }
  .overlay h1 {
    text-align:center;
    color:#fff;
    font-size: 25px;
    margin:5% 5%;
    text-shadow: 0 0 10px black;
  }
}
.overlay button {
  color: #fff;
  text-decoration: none;
  font-weight: bold;
  font-size: 18px;
  margin-top: 40px;
  margin-left: auto;
  margin-right: auto;
  background-color: #fa5ba5;
  padding: 20px 30px;
  border-radius: 30px;
  z-index: 99999;
}
</style>
