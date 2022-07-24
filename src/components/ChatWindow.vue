<script>
class Message {
	constructor(leftUser, text)
	{
		this.leftUser = leftUser;
		this.text = text;
	}
}

class User {
	constructor(name, imageName = "../placeholder.png")
	{
		this.name = name;
		this.imageLink = "/src/media/images/contacts/" + imageName;
	}
}

export default {
	data() {
		return {
			users: [
				new User ("VueBot", "VueBot.png"),
				new User ("rekkylaws")
			],
			messages: [
				new Message(true, "Hello !"),
				new Message(false, "Hi !")
			],
		}
	},
	methods: {
		getPositionClass(isLeft) {
			return isLeft ? "message-left" : "message-right";
		}
	}
}
</script>

<template>
	<div class="chat-window">
		<header>
			<img :src="users[0].imageLink" class="window-contact-image">
			<div class="window-contact-name">{{ users[0].name }}</div>
		</header>
		<div class="messages-container">
			<div class="message" v-for="message in messages" :class="getPositionClass(message.leftUser)">
				<img v-if="message.leftUser" :src="users[0].imageLink" class="message-image">
				<img v-else :src="users[1].imageLink" class="message-image">
				<div class="message-text">
					{{ message.text}}
				</div>
			</div>
		</div>
	</div>
</template>

<style>
header {
	width: 100%;
	height: 70px;
	background-color: #aaf2de;
	display: flex;
	align-items: center;
	gap: 15px;
}

.chat-window {
	position: fixed;
	top: 0;
	right: 0;
	width: calc(100% - 300px);
	height: 100vh;
	background-color: #1D1D1D;
}

.window-contact-image {
	height: 70%;
	width: auto;
	aspect-ratio: 1;
	border-radius: 50%;
	border: 3px solid white;
	background-color: white;
	margin-left: 25px;
}

.window-contact-name {
	font-size: 30px;
}

.messages-container {
	height: 100%;
}

.message {
	display: flex;
	align-items: center;
	gap: 15px;
	margin:  15px;
}

.message-image {
	aspect-ratio: 1;
	height: 50px;
	border-radius: 50%;
	border: 2px solid white;
	background-color: white;
}

.message-right {
	float: right;
	flex-direction: row-reverse;
}

.message-text {
	padding: 15px 10px;
	background-color: lightgray;
	border-radius: 20px;	
	font-size: 25px;
}
</style>