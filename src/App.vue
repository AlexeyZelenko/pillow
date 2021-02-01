<template>
<!--	<Vue3CountdownClock/>-->
	<div
			class="card mb-3"
	>
		<div
				class="card-body"
				ref="header"
				style="z-index: 999; background-color: cornflowerblue; width: 100%; max-height: 100px"
		>
			<p class="text-white">Телефони: 0966936001, 0633653655 , 0677045632</p>
			<p class="text-white-50 pb-2">Вайбер: 0966936001</p>
		</div>
		<img
				src="https://drive.google.com/uc?export=view&id=1YQTC25oWYfkMmrjt-FYR_Nt1ir_Za1dq"
				class="card-img-top"
				alt="feathers"
		>
	</div>

	<HelloWorld style="z-index: 1"/>


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
import { defineComponent, ref, provide } from 'vue'
import Vue3CountdownClock from 'vue3-clock-countdown'

export default {
  name: 'App',
	data() {
      return {
          scrollY: 0,
          elY: 0,
			}
	},
  components: {
    HelloWorld, Vue3CountdownClock
  },
    setup () {
        const deadLine = ref('2021/02/06 10:00:00 GMT-0200')
        provide('deadline', deadLine)

        const Title = ref('Online service will be honored through:')
        provide('title', Title)

        const timerStyle = ref({
            'text-align': 'center',
            'font-family': 'sans-serif',
            'font-weight': 50
        })
        provide('timerStyle', timerStyle)

        const h1Style = ref({
            color: '#396',
            'font-weight': 100,
            'font-size': '20px',
            margin: '40px 0px 20px'
        })
        provide('h1Style', h1Style)

        const clockdiv = ref({
            'font-family': 'sans-serif',
            color: '#fff',
            display: 'inline-block',
            'font-weight': 100,
            'text-align': 'center',
            'font-size': '30px'
        })
        provide('clockdiv', clockdiv)

        const clockdivDiv = ref({
            padding: '10px',
            'border-radius': '3px',
            background: '#00BF96',
            display: 'inline-block',
            margin: '1px'
        })
        provide('clockdivDiv', clockdivDiv)

        const clockdivDivSpan = ref({
            padding: '15px',
            'border-radius': '3px',
            background: '#00816A',
            display: 'inline-block'
        })
        provide('clockdivDivSpan', clockdivDivSpan)

        const styleEndTime = ref({
            color: '#fff'
        })
        provide('styleEndTime', styleEndTime)

        const smalltext = ref({
            'padding-top': '5px',
            'font-size': '10px'
        })
        provide('smalltext', smalltext)

        const titleDays = ref('Days')
        provide('titleDays', titleDays)

        const titleHours = ref('Hours')
        provide('titleHours', titleHours)

        const titleMinutes = ref('Minutes')
        provide('titleMinutes', titleMinutes)

        const titleSeconds = ref('Seconds')
        provide('titleSeconds', titleSeconds)

        const titleEndTime = ref('End Time!')
        provide('titleEndTime', titleEndTime)
    },
	created() {
			window.addEventListener('scroll', this.onScroll);
	},
	methods: {
			onScroll() {
					const el = this.$refs.header;
					const height = el.getBoundingClientRect().height;
					const pos = window.pageYOffset;
					const diff = this.scrollY - pos;

					this.elY = Math.min(0, Math.max(-height, this.elY + diff));
					el.style.position = pos >= height ? 'fixed' : pos === 0 ? 'absolute' : el.style.position;
					el.style.transform = `translateY(${el.style.position === 'fixed' ? this.elY : 0}px)`;

					this.scrollY = pos;
			},
	},
}
</script>

<style>
	body {
		margin: 0;
	}

	header {
		z-index: 999;
		position: absolute;
		top: 0;
		height: 100px;
		width: 100%;
	}
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
	p {
		font-size: 18px;
	}
	@media (max-width: 900px)  {
		p {
			font-size: 14px;
		}
	}
</style>
