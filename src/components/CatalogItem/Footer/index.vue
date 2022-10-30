<template>
   <div class="team">
      <div
              class="team--item"
              v-for="item in team"
              :key="item.id"
      >
         <div class="team--image">
            <img :src="`/src/assets/images/team/${item.src}.png`" alt="">
         </div>
         <div class="team--name">{{item.name}}</div>
         <div class="team--post">{{item.post}}</div>
      </div>
   </div>
</template>

<script>
export default {
   data() {
      return {
         team: [
            {
               id: 1,
               name: 'Юрій Бієвець',
               post: 'Основатель фонда',
               src: '1'
            },
            {
               id: 2,
               name: 'Андрій Кушнір',
               post: 'Специалист по связям с общественностью',
               src: '1'
            },
            {
               id: 3,
               name: 'Віталій Бієвець',
               post: 'Руководитель отдела по реализации проектов',
               src: '1'
            },
            {
               id: 4,
               name: 'Світлана Череватенко',
               post: 'секретар',
               src: '1'
            }
         ]
      }
   },
}
</script>

<style scoped lang="scss">
.team {
   display: flex;
   flex-direction: column;
   align-items: center;
   justify-content: space-around;
   margin: 30px 20px 100px;

   @media (min-width: 960px) {
      flex-direction: row;
   }

   &--item {
      max-width: 260px;
   }

   &--image {
      margin: 20px;
   }

   &--name {
      font-size: 22px;
      line-height: 1.35;
      font-family: 'Montserrat',Arial,sans-serif;
      font-weight: 600;
      color: rgb(0 0 0);
   }

   &--post {
      color: rgb(122 122 122);
      font-size: 14px;
      line-height: 1.55;
      font-family: 'Montserrat',Arial,sans-serif;
      font-weight: 300;
   }
}
</style>