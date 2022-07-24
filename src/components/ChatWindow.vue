<script>
class Message {
	constructor(leftUSer, text)
	{
		this.leftUSer = leftUSer;
		this.text = text;
	}
}

class User {
	constructor(name, isLeft, imageLink = "../placeholder.png")
	{
		this.name = name;
		this.isLeft = isLeft;
		this.imageLink = "/src/media/images/contacts/" + imageName;
	}
}

export default {
	data() {
		return {
			users: [
				{name: "VueBot", imageLink: "/src/media/images/contacts/VueBot.png"},
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
</style>