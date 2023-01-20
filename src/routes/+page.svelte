<script>
	import { onMount } from 'svelte';
	import { gsap } from 'gsap';
	import { ScrollTrigger } from 'gsap/ScrollTrigger';

	onMount(() => {
		gsap.registerPlugin(ScrollTrigger);
		gsap.to('main', {
			'--target': '0%',
			ease: 'none',
			scrollTrigger: {
				trigger: 'main',
				start: 'top top',
				end: '+=1000',
				pin: true,
				scrub: 1
			}
		});
	});
</script>

<svelte:head>
	<title>picole.ch</title>
</svelte:head>

<main>
	<h1>assiette.ch <span>restaurants en Suisse</span></h1>
	<a href="mailto:thomas.miller147@gmail.com">
		<svg
			xmlns="http://www.w3.org/2000/svg"
			fill="none"
			viewBox="0 0 24 24"
			stroke-width="1.5"
			stroke="black"
			class="w-6 h-6"
		>
			<path
				stroke-linecap="round"
				d="M16.5 12a4.5 4.5 0 11-9 0 4.5 4.5 0 019 0zm0 0c0 1.657 1.007 3 2.25 3S21 13.657 21 12a9 9 0 10-2.636 6.364M16.5 12V8.25"
			/>
		</svg>
	</a>
</main>

<style>
	main {
		--target: 100%;
		--color1: #ff0000;
		--color2: #fff;
		width: 100%;
		background: linear-gradient(to right, var(--color1) var(--target), var(--color2) var(--target));
		display: flex;
		height: 100vh;
		justify-content: center;
		align-items: center;
	}

	h1 {
		color: var(--color2);
		font-size: clamp(2.5rem, 8vw, 6rem);
		text-align: center;
		background: linear-gradient(to right, var(--color2) var(--target), var(--color1) var(--target));
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
		width: 100%;
		display: block;
		line-height: 1;
	}

	h1 span {
		margin-top: 20px;
		font-size: 0.5em;
		display: block;
		font-weight: 300;
	}

	a {
		position: fixed;
		width: 30px;
		bottom: 20px;
		right: 40px;
		z-index: 10;
	}
</style>
