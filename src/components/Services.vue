<template>
	<div class="card">
		<img
				:src="service.img"
				alt="pillow"
				class="card-img-top"
		>
		<div class="card-body">
			<h3 class="card-title">{{service.title}}</h3>
		</div>
		<!-- Button trigger modal -->
		<button
				:data-bs-target="service.button"
				class="btn btn-primary"
				data-bs-toggle="modal"
				type="button"

		>
			Більше
		</button>
	</div>
</template>

<script>
    export default {
        name: "Services",
        props: {
            service: {
                type: Object
            }

        }
    }

</script>

<style scoped>

</style>