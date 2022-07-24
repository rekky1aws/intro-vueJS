<script>
class Contact {
	constructor (name, imageName = "../placeholder.png")
	{
		this.name = name;
		this.imageLink = "/src/media/images/contacts/" + imageName;
	}
}

class Message {
	constructor (isSender, text)
	{
		this.isSender = isSender,
		this.text = text,

	}
}

export default {
	data() {
		return {
			users: [

			],
			messages: [
				new Message(false, "Hello !"),
			]
		}
	}
}

</script>

<template>
	<div class="chat-window">
		<header>
			
		</header>
	</div>
</template>

<style>
body {
	overflow: hidden;
}

header {
	width: 100%;
	height: 70px;
	background-color: #aaf2de;
}

.chat-window {
	position: fixed;
	top: 0;
	right: 0;
	width: calc(100% - 300px);
}
</style>