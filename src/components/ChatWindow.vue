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
			<div class="message" v-for="message in messages">
				<img v-if="message.leftUser" :src="users[0].imageLink" class="message-image">
				<img v-else :src="users[1].imageLink" class="message-image">
				<div class="message-text" v-if="message.leftUser" >
					
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
</style>