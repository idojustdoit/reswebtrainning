<template>
	<div class="clearAll">
		<span class="clearBtn" @click="clearData">Clear All</span>
	</div>
</template>

<script>
export default {
	methods: {
		clearData() {
			this.$emit('removeAll');
		}
	}
}
</script>

<style>
	.clearAll {
		width: 8.5rem;
		height: 50px;
		line-height: 50px;
		background-color: white;
		border-radius: 50x;
		margin: 0 auto;
	}

	.clearBtn {
        cursor: pointer;
		color: #e20303;
		display: black;
	}
</style>