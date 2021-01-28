<template>
	<!-- Modal -->
	<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
		<div class="modal-dialog">
			<div class="modal-content">
				<div class="modal-header">
					<h5 class="modal-title" id="exampleModalLabel">Реставрація подушок.</h5>
					<button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
				</div>
				<div class="modal-body">
					<h3>
						70*70-120грн
					</h3>
					<h3>70*50-100грн</h3>
					<h3>60*60-100грн</h3>
					<h3>50*50-90грн</h3>
					<h3>40*60-90грн</h3>
					<h3>40*40-80грн</h3>
				</div>
				<div class="modal-footer">
					<button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Вийти</button>
				</div>
			</div>
		</div>
	</div>
	<div class="modal fade" id="exampleModal2" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
		<div class="modal-dialog">
			<div class="modal-content">
				<div class="modal-header">
					<h5 class="modal-title" id="exampleModalLabel">Реставрація ковдр.</h5>
					<button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
				</div>
				<div class="modal-body">
					<h3>Односпальне-1,40*2-800грн</h3>
					<h3>Полуторне-1,50*2-900</h3>
					<h3>Двоспальне 1,75*2-1000</h3>
					<h3>Євро 2,1*2,2 -1200</h3>
				</div>
				<div class="modal-footer">
					<button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Вийти</button>
				</div>
			</div>
		</div>
	</div>
	<div class="modal fade" id="exampleModal3" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
		<div class="modal-dialog">
			<div class="modal-content">
				<div class="modal-header">
					<h5 class="modal-title" id="exampleModalLabel">Реставрація перин.</h5>
					<button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
				</div>
				<div class="modal-body">
					<h3>від 500грн до 1000 в залежності від розміру.</h3>
				</div>
				<div class="modal-footer">
					<button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Вийти</button>
				</div>
			</div>
		</div>
	</div>
	<div class="modal fade" id="exampleModal4" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
		<div class="modal-dialog">
			<div class="modal-content">
				<div class="modal-header">
					<h5 class="modal-title" id="exampleModalLabel">Пошиття постільної білизни</h5>
					<button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
				</div>
				<div class="modal-body">
					<h4>Постільна білизна від 700 грн до 1200 залежить
						від розміру і гатунку тканини.</h4>
				</div>
				<div class="modal-footer">
					<button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Вийти</button>
				</div>
			</div>
		</div>
	</div>

	<div	class="container">
		<div	class="row row-cols-1 row-cols-md-2 g-4">
			<div class="col py-2"
					 v-for="service in services"
					 :key="service.id"
			>
				<Services :service="service"/>
			</div>
		</div>
	</div>

</template>

<script>
	import Services from './Services.vue'

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
	components: {
      Services
	},
  data() {
    return {
      count: 0,
			services: [
					{
					    id: 1,
					    img: 'https://drive.google.com/uc?export=view&id=1VW90BWZ4tY-BSdVk8OKe4byvODNvzMd1',
							alt: '',
							title: 'Реставрація подушок.',
							button: '#exampleModal'
					},
          {
              id: 2,
              img: 'https://drive.google.com/uc?export=view&id=1AhRqLSPXlizdyL80d1sNQjM8-3R5GpVh',
              alt: '',
              title: 'Реставрація ковдр.',
              button: '#exampleModal2'
          },
          {
              id: 3,
              img: 'https://drive.google.com/uc?export=view&id=17LedA1pIJjcNyh-wLp08o0syZ1qQvAFy',
              alt: '',
              title: 'Реставрація перин.',
              button: '#exampleModal3'
          },
          {
              id: 4,
              img: 'https://drive.google.com/uc?export=view&id=1gf9Be7l_SN-TQmA6ajzIkeRa40Dnce7t',
              alt: '',
              title: 'Пошиття постільної білизни',
              button: '#exampleModal4'
          }
			]
    }
  }
}
</script>
