<script setup>
import BurgerMenuIcon from './icons/BurgerMenuIcon.vue'
</script>

<script>
class Contact {
	constructor (name, imageName = "../placeholder.png", status = false)
	{
		this.name = name;
		this.imageLink = "/src/media/images/contacts/" + imageName;
		this.isConnected = status;
	}
}


export default {
	data () {
		return {
			contacts: [
				new Contact("VueBot", "VueBot.png", true),
				new Contact("Jean Mich")
			]
		}
	}
}
</script>

<template>
	<div class="contact-list">
		<div class="top-menu">
			<button class="burger-button cliquable">
				<BurgerMenuIcon />
			</button>
			<h1>Vue Chat</h1>
		</div>
		<div class="contacts-container">
			<div class="contact" v-for="contact in contacts">
				<img :src="contact.imageLink" :alt="contact.name" class="contact-picture">
				<div class="contact-name">{{ contact.name }}</div>
				<div v-if="contact.isConnected" class="contact-online contact-status"></div>
				<div v-else class="contact-not-online contact-status"></div>
			</div>
		</div>
	</div>
</template>

<style>
.burger-button {
	height: 30px;
	width: 30px;
	padding: 0;
	border: none;
	background-color: #FFF0;
}

.cliquable {
	transition: linear 0.1s;
}

.cliquable:hover {
	transform: scale(1.05);
}

.cliquable:active {
	transform: scale(0.9);
}

.contact-list {
	background-color: #2d3342;
	height: 100%;
	width: 300px;
	position: fixed;
	top: 0;
	left: 0;
}

.top-menu {
	height: 70px;
	width: 100%;
	background-color: #3ec8a0;
	display: flex;
	justify-content: space-between;
	align-items: center;
	padding: 15px;
}

.contacts-container {
	display: flex;
	flex-direction: column;
}

.contact {
	height: 70px;
	width: 100%;
	display: flex;
	align-items: center;
	gap: 15px;
	padding: 5px;
	padding-left: 15px;
	transition: ease-in-out 0.2s;
}

.contact:hover {
	background-color: #1d1d1d1d;
	-webkit-box-shadow: 0 0 10px 3px rgba(255, 255, 255, 0.05);
	-moz-box-shadow: 0 0 10px 3px rgba(255, 255, 255, 0.05);
	box-shadow: 0 0 10px 3px rgba(255, 255, 255, 0.05);
	}

.contact-picture {
	height: 75%;
	aspect-ratio: 1;
	width: auto;
	border-radius: 50%;
	background-color: white;
	padding: 1%;
}

.contact-name {
	color: white;
	font-weight: white;
	font-size: 25px;
}

.contact-status {
	height: 10px;
	width: 10px;
	border-radius: 50%;
	border: 1px solid black;
}

.contact-online {
	background-color: #3ec8a0;
}

.contact-not-online {
	background-color: red;
}

</style>