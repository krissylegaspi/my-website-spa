<template>
	<div>
		<div class="nav-bar" id="nav">
			<ul>
				<nuxt-link to="/">HOME</nuxt-link>
				<nuxt-link to="/portfolio">PORTFOLIO</nuxt-link>
        		<!-- <nuxt-link to="/shop">SHOP</nuxt-link> -->
        		<nuxt-link to="/blog">BLOG</nuxt-link>
				<nuxt-link to="/about">ABOUT</nuxt-link>
        		<!-- <nuxt-link to="/contact" id="pls">HIRE ME</nuxt-link> -->
        		<a href="mailto:contact@kristinelegaspi.com" id="pls">HIRE ME</a>
			</ul>
		</div>

		<Nuxt />
	</div>
</template>

<style scoped>

.nav-bar {
    width: 100%;
    font-family: 'Cutive Mono', monospace;
    text-align: center;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    padding-bottom: 40px;
	padding-top: 40px;
}

.nav-bar .ul {
    display: flex;
    list-style-type: none;
}

/* #pls {
    color: rgb(255, 113, 137);
} */

#pls:hover {
    color: rgb(255, 113, 137);
}

.nav-bar .ul .active {
    color: var(--highlight);
	text-decoration: none;
}

.nav-bar .ul .active:hover, .nav-bar .ul .active:before {
    opacity: 0;
	text-decoration: none;
}

.nav-bar a {
    font-size: 26px;
    color: var(--text);
    /* font-weight: bold; */
    text-decoration: none;
    margin: 0px 10px;
    padding: 10px 10px;
    position: relative;
    z-index: 0;
    cursor: pointer;
    font-family: 'Cutive Mono', monospace;
}

.nav-bar a:before, .nav-bar a:after
{
    position: absolute;
    opacity: 0;
    font-size: 30px;
    top: 0px;
    bottom: 2px;
    transition: all 0.3s;
    font-family: 'Cutive Mono', monospace;
    text-align: center;
}

.nav-bar a:before
{
    content: '(';
    font-size: 43px;
    letter-spacing: 1px;
    left: 0px;
    transform: translateX(10px);
    font-family: 'Cutive Mono', monospace;
    text-align: center;
}

.nav-bar a:after
{
    content: ')';
    font-size: 43px;
    letter-spacing: 1px;
    right: 0px;
    transform: translateX(-10px);
    font-family: 'Cutive Mono', monospace;
    text-align: center;
}

.nav-bar a:hover:before, .nav-bar a:hover:after
{
    opacity: 1;
    letter-spacing: -10px;
    transform: translateX(-5px);
    font-family: 'Cutive Mono', monospace;
    text-align: center;
}

html {
  	font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
	font-size: 16px;
	word-spacing: 1px;
	-ms-text-size-adjust: 100%;
	-webkit-text-size-adjust: 100%;
	-moz-osx-font-smoothing: grayscale;
	-webkit-font-smoothing: antialiased;
	box-sizing: border-box;
}

*,
*::before,
*::after {
	box-sizing: border-box;
	margin: 0;
}

.button--green {
	display: inline-block;
	border-radius: 4px;
	border: 1px solid #3b8070;
	color: #3b8070;
	text-decoration: none;
	padding: 10px 30px;
}

.button--green:hover {
	color: #fff;
	background-color: #3b8070;
}

.button--grey {
	display: inline-block;
	border-radius: 4px;
	border: 1px solid #35495e;
	color: #35495e;
	text-decoration: none;
	padding: 10px 30px;
	margin-left: 15px;
}

.button--grey:hover {
	color: #fff;
	background-color: #35495e;
}
</style>
