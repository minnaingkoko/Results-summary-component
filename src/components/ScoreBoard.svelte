<script lang="ts">
	export let icon: string, text: string, score: number, color: string;
</script>

<div class="score_board" style="background-color: hsla({color}, 0.05)">
	<div class="score_type">
		<img src={icon} alt="" />
		<div style="color: hsl({color})" class="text3"><b>{text}</b></div>
	</div>
	<div class="score_result"><b>{score}</b> / 100</div>
</div>

<style>
	.score_board {
		@apply flex flex-row justify-between py-[16px] px-[8px] rounded-[10px] mb-[12px];
	}
	.score_type {
		@apply flex flex-row items-center gap-[8px];
	}
</style>
