<template>
  <div ref="el" class="catalog-item">
    <div v-if="pray">
      <Pray/>
    </div>
    <div
      class="sec-text"
    >
      <h3 class="sec-text__title">{{title}}</h3>
      <p class="sec-text__dsc">{{text}}</p>
    </div>
     <div v-if="footer">
        <Footer/>
     </div>
    <section
      ref="el"
      :class="isShown ? sectionClass : null"
    ></section>
  </div>
</template>

<script>
import { ref, computed, onMounted, onBeforeUnmount } from 'vue'
import useIntersectionObserver from '../../composables/useIntersectionObserver'
import Pray from './Pray/index.vue'
import Footer from './Footer/index.vue'

export default {
  name: 'CatalogItem',
  components: { Pray, Footer },
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
     const footer = computed(
             () => props.data.footer
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
      pray,
      footer
    }
  }
}
</script>

<style scoped lang="scss">
  body {margin: 0;padding: 0;font-family: sans-serif;color: #262626;}

  section {
    width: 100%;
    height: 100vh;
    box-sizing: border-box;
  }
  section.sec1 {
    background: url('../../assets/images/причастие.jpg')  no-repeat center / cover;
    background-attachment: fixed;
  }
  section.sec2 {
    background: url('../../assets/images/nightPrayer.jpg') no-repeat center / cover;
    background-attachment: fixed;
  }
  section.sec3 {
    background: url('../../assets/images/song.jpg')no-repeat center / cover;
    background-attachment: fixed;
  }
  section.sec4 {
    background: url('../../assets/images/fire.jpg')no-repeat center / cover;
    background-attachment: fixed;
  }
  section.sec5 {
    background: url('../../assets/images/water.jpg')no-repeat center / cover;
    background-attachment: fixed;
  }
  section.sec6 {
    background: url('../../assets/images/centreHelp.jpg')no-repeat center / cover;
    background-attachment: fixed;
  }
  section.sec7 {
    background: url('../../assets/images/homegroup.jpg')no-repeat center / cover;
    background-attachment: fixed;
  }
  section.sec8 {
    background: url('../../assets/images/help.jpg')no-repeat center / cover;
    background-attachment: fixed;
  }
  section.sec9 {
    background: url('../../assets/images/footer/footer.png')no-repeat center / cover;
    background-attachment: fixed;
  }
  .sec-text {
    padding: 1% 8%;
    height: auto;
  }
  .sec-text__title {
     margin-bottom: 40px;
     font-size: 42px;
     line-height: 1.23;
     font-family: 'Montserrat',Arial,sans-serif;
     font-weight: 600;
     color: rgb(0 0 0);
  }
  .sec-text__dsc {
     max-width: 560px;
     font-size: 24px;
     line-height: 1.5;
     font-family: 'Montserrat',Arial,sans-serif;
     font-weight: 300;
     color: rgb(0 0 0);
     margin: 0 auto;
  }
</style>
