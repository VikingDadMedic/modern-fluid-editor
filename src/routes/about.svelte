<script>
	import Image from 'svimg';
</script>

<main>
	<h1 class="title">
		<div class="title__text">About Voyager Design Editor</div>
		<div class="graphics" />
	</h1>
	<section class="intro">
		<p>
			Voyager's Design Editor is a graphic design platform, used to create social media graphics, presentations, posters, documents and other visual content. 
			The app includes templates for users to use. .
		</p>

</main>

<style>
	main {
		@media (--mq-tablet-min) {
			font-size: var(--font-size-medium);
		}
	}

	.title {
		font-size: clamp(2rem, 6vw + 1rem, 32rem);
		line-height: 1.25;
		min-height: calc(100vh - 100px - var(--spacing-2));
		display: flex;
		justify-content: center;
		align-items: center;
		margin: 0;
		position: relative;
		overflow: hidden;
		margin-bottom: var(--spacing-3);
		border-bottom: 4px solid var(--color-secondary-faded);
	}

	.graphics {
		min-width: 200vw;
		height: 100%;
		position: absolute;
		left: -50%;
		transform: perspective(50vh) rotate3d(1, 0, 0, 70deg);
		background-image: repeating-linear-gradient(
				90deg,
				var(--color-secondary-faded) 0%,
				transparent 2px,
				transparent var(--spacing-2),
				var(--color-secondary-faded) calc(var(--spacing-2) + 2px)
			),
			repeating-linear-gradient(
				180deg,
				var(--color-secondary-faded) 0%,
				transparent 2px,
				transparent var(--spacing-2),
				var(--color-secondary-faded) calc(var(--spacing-2) + 2px)
			);
		z-index: var(--level-n1);
		animation: movement 0.7s linear infinite;
	}

	.title__text {
		width: fit-content;
		text-align: center;
		max-width: 10em;
		line-height: 1.2;
		margin-bottom: var(--spacing-4);
		text-shadow: 0 0 var(--spacing-n2) var(--color-primary-tint);
		animation: glow 2s infinite linear alternate;
	}

	h2 {
		font-size: var(--font-size-large);
		margin-bottom: var(--spacing-1);
	}

	h3 {
		font-size: var(--font-size-medium);
		margin-top: var(--spacing-1);
		margin-bottom: var(--spacing-n1);
	}

	dt {
		color: var(--color-secondary);
		font-family: var(--font-family-mono);
		margin-top: var(--spacing-1);
		margin-bottom: var(--spacing-n2);
	}

	a {
		color: var(--color-secondary);
		text-decoration: none;
		font-weight: var(--font-weight-bold);
	}

	a:hover,
	a:active,
	a:focus {
		text-decoration: underline;
	}

	pre {
		display: inline-block;
		border: 2px solid var(--color-secondary);
		background-color: var(--color-secondary-faded);
		border-radius: var(--spacing-n2);
		padding: var(--spacing-1);
		font-weight: var(--font-weight-bold);
		margin-bottom: var(--spacing-n1);
		overflow: auto;
		max-width: 100%;
	}

	section {
		max-width: 820px;
		margin: 0 auto;
		margin-bottom: var(--spacing-2);
		padding: 0 var(--spacing-n1);

		@media (--mq-tablet-min) {
			padding: 0 var(--spacing-2);
		}
	}

	p + p {
		margin-top: var(--spacing-1);
	}

	figure {
		display: block;
		margin: var(--spacing-2) 0;

		@media (--mq-desktop-min) {
			margin: var(--spacing-2) calc(-1 * var(--spacing-4));
			width: calc(100% + 2 * var(--spacing-4));
		}
	}

	figcaption {
		text-align: center;
		margin-top: var(--spacing-n1);
		font-size: var(--font-size-small);
		@media (--mq-tablet-min) {
			font-size: var(--font-size-base);
		}
		@media (--mq-desktop-min) {
			padding: 0 var(--spacing-3);
		}
	}

	figure :global(img) {
		max-width: 100%;
		margin: 0 auto;
		display: block;
	}

	@keyframes movement {
		0% {
			transform: perspective(50vh) rotate3d(1, 0, 0, 70deg) translate3d(0, -var(--spacing-2), 0);
		}
		100% {
			transform: perspective(50vh) rotate3d(1, 0, 0, 70deg) translate3d(0, var(--spacing-2), 0);
		}
	}

	@keyframes glow {
		0% {
			text-shadow: 0 0 0.1em var(--color-primary-tint);
		}
		100% {
			text-shadow: 0 0 0.25em var(--color-primary-tint);
		}
	}
</style>
