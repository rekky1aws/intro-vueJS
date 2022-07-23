<script>

</script>

<template>
	<div class="burger-container">
		<div class="burger-part"></div>
		<div class="burger-part"></div>
		<div class="burger-part"></div>
	</div>
</template>

<style>
.burger-container {
	aspect-ratio: 1;
	height: min(100%, auto);
	width:  min(100%, auto);
	display: flex;
	flex-direction: column;
	justify-content: space-between;
	align-items: center;
}

.burger-part {
	width: 100%;
	height: 20%;
	background-color: #2d3342;
	border-radius: 5px;
}
</style>