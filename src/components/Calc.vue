<template>
	<div id="calc">
		<h1 class="app-title">{{ title }}</h1>
		
		<div class="calc-wrapper">
			<div class="equation">{{ equation }}</div>
			<div class="result">= {{ result }}</div>
			<div class="numbers-wrapper">
				<button class="spbtn cbtn" @click="clearRes">C</button>
				<button @click="intInputs(0)">0</button>
				<button @click="intInputs(1)">1</button>
				<button class="spbtn" @click="intInputs('+')">+</button>
				<button @click="intInputs(2)">2</button>
				<button @click="intInputs(3)">3</button>
				<button @click="intInputs(4)">4</button>
				<button class="spbtn" @click="intInputs('-')">-</button>
				<button @click="intInputs(5)">5</button>
				<button @click="intInputs(6)">6</button>
				<button @click="intInputs(7)">7</button>
				<button class="spbtn" @click="intInputs('*')">*</button>
				<button @click="intInputs(8)">8</button>
				<button @click="intInputs(9)">9</button>
				<button class="spbtn" @click="intInputs('.')">.</button>
				<button class="spbtn" @click="intInputs('/')">/</button>
				<button class="spbtn" @click="calRes">=</button>
			</div>
		</div>
	</div>
</template>

<script>
	export default {

		data() {
			return {
				title: 'Calculator',
				equation: 0,
				result: '',
			}
		},

		methods: {
			intInputs: function(x) {
				this.equation += x;
			},

			calRes() {
				if(this.equation === '') {
					this.result = 'Please Add equation!';
				} else {
					this.result = eval(this.equation);
				}
			},

			clearRes() {
				this.equation = '';
				this.result = '';
			}
		}

	}
</script>

<style>
	@import url('https://fonts.googleapis.com/css?family=Raleway:100,200,300,400');
	@import url('https://fonts.googleapis.com/css?family=Anton|PT+Sans+Narrow');
	
	.app-title {
	    font-family: 'PT Sans Narrow', sans-serif;
	}

	.spbtn {
		background: #868e8a;
		color: white;
		font-weight: 100;
	}

	.cbtn {
		background: #841f1f;
	}

	.equation,
	.result {
		background: #3c3b3b;
	    text-align: left;
	    color: #1cbb64;
	    font-size: 15px;
	    font-family: 'PT Sans Narrow', sans-serif;
	}

	.equation {
		padding: 15px 15px 0 15px;
	}

	.result {
		padding: 0 15px 15px 15px;
	}

	.calc-wrapper {
		width: 26vw;
    	margin: 0 auto;
	}

	button {
		font-family: 'Raleway', sans-serif;
		flex-grow: 1;
		width: 25%;
		height: 87px;
		border: 1px solid #3c3b3b;
		background: #2b2b2b;
		font-size: 36px;
		color: #779082;
		cursor: pointer;
	}

	.numbers-wrapper {
		width: 100%;
    	display: flex;
		flex-wrap: wrap;
	}
</style>