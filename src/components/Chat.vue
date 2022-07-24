<script setup>
	import ContactList from './ContactList.vue'
	import ChatWindow from './ChatWindow.vue'
</script>

<script>
export default {
	data() {
		return {

		}
	}
}
</script>

<template>
	<div class="app-container">
		<ContactList />
		<ChatWindow />
	</div>
</template>

<style>
.app-container {
	height: 100vh;
	width: 100vw;
	display: grid;
	grid-template-rows: 300px, calc(100% - 300px);
}

</style>
