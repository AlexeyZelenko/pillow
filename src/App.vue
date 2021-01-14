<template>
<!--  <img alt="Vue logo" src="~/assets/logo.png" />-->
	<div class="card mb-3">
		<img
				src="https://drive.google.com/uc?export=view&id=1YQTC25oWYfkMmrjt-FYR_Nt1ir_Za1dq"
				class="card-img-top"
				alt="feathers"
		>
		<div class="card-body" style="background-color: cornflowerblue">
<!--			<h5 class="card-title">Card title</h5>-->
<!--			<p class="card-text">Реставрація подушок, ковдр, перин.</p>-->
<!--			<p class="card-text">Пошиття постільної білизни.</p>-->
			<p class="text-white">Телефони: 0966936001, 0633653655 , 0677045632</p>
			<p class="text-white-50">Вайбер: 0966936001</p>
		</div>
	</div>

  <HelloWorld msg="Наші послуги" />

	<footer>
		<div>
			<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d733.6029174975548!2d32.10251774294741!3d49.419197637518145!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zNDnCsDI1JzEwLjIiTiAzMsKwMDYnMTIuOCJF!5e0!3m2!1sru!2sua!4v1610618716700!5m2!1sru!2sua" frameborder="0" style="border:0;" allowfullscreen="" aria-hidden="false" tabindex="0"></iframe>
			<div>
				<div class="brand">{{ new Date().getFullYear() }} — Галина Філатова</div>
			</div>
		</div>
	</footer>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
	iframe {
		width: 100%;
		height: 640px;
	}
	/* Footer */
	footer {
		clear: both;
		padding-top: 50px;
		padding-bottom: 40px;
		text-align: center;
		background-color: #38404b;
		margin-top: 30px;
	}

	footer .brand {
		color: #bcc9dd;
	}

	footer .menu li {
		padding-left: 10px;
		padding-right: 10px;
	}

	footer .menu li a {
		color: #bcc9dd;
	}

	footer .menu {
		display: inline-block;
		margin-top: 30px;
		margin-bottom: 15px;
	}

	footer .copyright {
		font-size: 12px;
		color: #eee;
	}
</style>
