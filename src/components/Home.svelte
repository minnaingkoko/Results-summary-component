<script>
	// @ts-nocheck

	import ScoreBoard from './ScoreBoard.svelte';
	import data from '../data/data.json';
</script>

<main class="home">
	<div class="container">
		<div class="left">
			<div class="text">Your Result</div>
			<div class="score_circle">
				<div class="text1">76</div>
				<div class="text2">of 100</div>
			</div>
			<div class="grade">Great</div>
			<div class="result">You scored higher than 65% of the people who have taken these tests.</div>
		</div>
		<div class="right">
			<div class="heading">Summary</div>
			{#each data as item}
				<ScoreBoard icon={item.icon} text={item.category} score={item.score} color={item.color} />
			{/each}
			<div class="continue">Continue</div>
		</div>
	</div>
</main>

<style>
	.home {
		@apply w-screen h-screen flex justify-center items-center;
	}
	.container {
		@apply flex flex-row w-[700px] h-[500px] rounded-[36px];
		box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
	}
	.left {
		@apply flex flex-col items-center w-[350px] h-[100%] rounded-[36px] pt-[32px] pb-[32px];
		background-image: linear-gradient(hsl(252, 100%, 67%), hsl(241, 81%, 54%));
	}
	.text {
		@apply text-[24px] text-[#c8c7ff] font-bold;
	}
	.score_circle {
		@apply flex flex-col justify-center items-center w-[150px] h-[150px] rounded-[50%] mt-[32px];
		background-image: linear-gradient(hsla(256, 72%, 46%, 1), hsla(241, 72%, 46%, 0));
	}
	.text1 {
		@apply text-[64px] text-[#ffffff] font-bold;
	}
	.text2 {
		@apply text-[#c8c7ff];
	}
	.grade {
		@apply text-[#ffffff] font-bold text-[24px] mt-[16px];
	}
	.result {
		@apply w-[230px] text-[#c8c7ff] text-center mt-[16px];
	}
	.right {
		@apply w-[350px] h-[100%] rounded-tr-[36px] rounded-br-[36px] bg-[#ffffff] px-[32px] py-[24px] flex flex-col;
	}
	.heading {
		@apply font-extrabold text-[24px] mb-[32px];
	}
	.continue {
		@apply flex justify-center items-center w-[100%] h-[54px] cursor-pointer rounded-[32px] mt-[20px] duration-300 bg-[#303b5a] text-[#ffffff];
	}
	.continue:hover {
		background-image: linear-gradient(hsl(252, 100%, 67%), hsl(241, 81%, 54%));
	}
	@media only screen and (min-width: 700px) {
		.container {
			width: 700px;
			height: 500px;
		}
	}

	@media only screen and (max-width: 699px) {
		.home {
			display: block;
		}
		.container {
			width: 100%;
			flex-direction: column;
			border-radius: 0;
		}
		.left {
			border-radius: 0 0 36px 36px;
			width: 100%;
		}
		.right {
			border-radius: 0;
			width: 100%;
		}
	}
</style>
