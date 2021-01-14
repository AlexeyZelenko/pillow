<template>
  <h1>{{ msg }}</h1>

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

	<div
			class="container"
	>
		<div class="row row-cols-1 row-cols-md-2 g-4">
			<div class="col">
				<div class="card">
					<img
							src="https://drive.google.com/uc?export=view&id=1VW90BWZ4tY-BSdVk8OKe4byvODNvzMd1"
							class="card-img-top"
							alt="pillow"
					>
					<div class="card-body">
						<h3 class="card-title">Реставрація подушок.</h3>
					</div>
					<!-- Button trigger modal -->
					<button
							type="button"
							class="btn btn-primary"
							data-bs-toggle="modal"
							data-bs-target="#exampleModal"

					>
						Більше
					</button>
				</div>
			</div>
			<div class="col">
				<div class="card">
					<img
							src="https://drive.google.com/uc?export=view&id=1AhRqLSPXlizdyL80d1sNQjM8-3R5GpVh"
							class="card-img-top"
							alt="carpet"
					>
					<div class="card-body">
						<h3 class="card-title">Реставрація ковдр.</h3>
					</div>
					<!-- Button trigger modal -->
					<button
							type="button"
							class="btn btn-primary"
							data-bs-toggle="modal"
							data-bs-target="#exampleModal2"

					>
						Більше
					</button>
				</div>
			</div>
			<div class="col">
				<div class="card h-100">
					<img
							src="https://drive.google.com/uc?export=view&id=17LedA1pIJjcNyh-wLp08o0syZ1qQvAFy"
							class="card-img-top"
							alt="feather bed"
					>
					<div class="card-body">
						<h3 class="card-title">Реставрація перин.</h3>
					</div>
					<!-- Button trigger modal -->
					<button
							type="button"
							class="btn btn-primary"
							data-bs-toggle="modal"
							data-bs-target="#exampleModal3"

					>
						Більше
					</button>
				</div>
			</div>
			<div class="col">
				<div class="card">

					<img
							src="https://drive.google.com/uc?export=view&id=1gf9Be7l_SN-TQmA6ajzIkeRa40Dnce7t"
							class="card-img-top"
							alt="postal"
					>
					<div class="card-body">
						<h3 class="card-title">Пошиття постільної білизни</h3>
					</div>
					<!-- Button trigger modal -->
					<button
							type="button"
							class="btn btn-primary"
							data-bs-toggle="modal"
							data-bs-target="#exampleModal4"

					>
						Більше
					</button>
				</div>
			</div>
		</div>
	</div>

</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      count: 0,
			services: [
					{
					    img: '',
							alt: '',
							title: 'Card title',
							text: ''
					}
			]
    }
  }
}
</script>
