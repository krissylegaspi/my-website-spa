<template >
  	<div>
		<div class="index">
			<div class="pfp">
				<img src="../assets/profile-new.jpg" />
			</div>
			<div class="tag">
				<h1>{{ title }}</h1>
				<a href="mailto:contact@kristinelegaspi.com" target="_blank">
					<fa icon="envelope" id="fontawesome" /></a>
				<p>MS in Computer Science at Georgia Tech</p>
				<div class="socials">
					<a href="https://www.linkedin.com/in/kristine-legaspi/" target="_blank">
						<fa :icon="['fab', 'linkedin-in']" id="icons" />
					</a>
					<a href="https://github.com/krissylegaspi" target="_blank">
						<fa :icon="['fab', 'github']" id="icons" />
					</a>
					<a href="https://codepen.io/krissylegaspi" target="_blank">
						<fa :icon="['fab', 'codepen']" id="icons" />
					</a>
					<a href="./assets/Legaspi.Kristine.Resume.pdf" target="_blank">
						<fa :icon="['far', 'file-alt']" id="icons" />
					</a>
				</div>
			</div>
		</div>
  	</div>
</template>

<script>

export default {
  	name: "Index",
    props: {
        title: {
            type: String,
            default: "Kristine Legaspi"
        }
    }
}

</script>

<style>

html {
    margin-left: calc(100vw - 100%); /* Need to redo in order for this to work with dark mode enabled */
    margin-right: 0;
	background-color: rgb(253, 253, 253);
}

* {
    margin: 0;
    padding: 0;
    font-family: 'Lexend', sans-serif;
}

.index {
    position: fixed;
    width: 650px;
	margin-top: 200px;
	margin: auto;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    box-sizing: border-box;
    background: transparent;
    display: flex;
}

.index .pfp img {
  	border-radius: 50%;
  	border: 5px pink solid;
}

.index .tag {
	padding-top: 30px;
	width: 400;
	align-items: center;
}

.index .tag p {
	margin: 0;
	padding-left: 30px;
	text-align: justify;
	display: flex;
	margin-bottom: 1rem;
	font-family: 'Lexend', sans-serif;
	color: black;
}

.socials {
	width: 100%;
	text-align: center;
	padding-top: 10px;
	margin: auto;
}

.socials #icons {
	display: inline-block;
	font-size: 28px;
	/* padding-bottom: 15px; */
	color: rgb(255, 154, 171);
	font-size: 20px;
	padding-left: 10px;
	padding-right: 10px;
}

.socials #icons:hover {
	color: pink;
	opacity: 80;
}

.index h1 {
    margin: 0;
    padding-left: 30px;
    padding-right: 10px;
	padding-bottom: 10px;
    /* display: inline-grid; */
	display: inline-block;
    margin-bottom: 1rem;
    font-weight: normal;
    font-family: 'Roboto Mono', monospace;
}

/* Font Awesome icons */

#fontawesome {
    /* padding-top: 10px;
    padding-right: 10px;
    padding-left: 10px;
    padding-bottom: 10px; */
    display: inline-block;
	font-size: 28px;
	/* padding-bottom: 15px; */
	color: rgb(255, 154, 171);
	font-size: 25px;
}

#fontawesome:hover {
	color: pink;
	opacity: 80;
}

</style>