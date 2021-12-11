<script>
	import { currentSubtitle } from 'src/stores/currentSubtitle';

	import { onMount } from 'svelte';

	const subtitles = [
		'Willed into existence by',
		'Cybernatically enchanced by',
		'Found bugs in the app? Blame ',
		'Joy sparked by',
		'Made on Arrakis by',
		'Space-time folded by',
		'Spice harvested by',
		'Transmogrified into existence by',
		'Created according to the Great Convention by',
		'As decreed by Leto II, this was created by',
		'Created according to the Shadow Proclamation by',
		'Created according to the Codex Astartes by',
		'Blessed by Shai Hulud and made by',
	];

	let hasChanged = false;

	onMount(() => {
		if ($currentSubtitle) {
			return;
		}

		hasChanged = true;

		currentSubtitle.set(subtitles[Math.floor(Math.random() * subtitles.length)]);
	});
</script>

<header class="header">
	<div class="header__wrapper">
		<div>
			<h1 class="header__title">
				<a class="header__link header__link--title" href="/"> Voyager Social </a>
			</h1>
			<h2 class:header__subtitle--ready={$currentSubtitle && hasChanged} class="header__subtitle">
				{#if $currentSubtitle}
					{$currentSubtitle}
					<a
						class="header__link header__link--subtitle"
						href="http://codeadrian.github.io"
						target="_blank"
						rel="noopener noreferrer"
					>
						ARQITEQT
					</a>
				{:else}
					<a href="/">&nbsp; </a>
				{/if}
			</h2>
		</div>

		<nav>
			<ul class="header__list">
				<li><a class="header__link header__link--page" href="/about">About</a></li>
				<li>
					<a
						href="/"
						target="_blank"
						class="header__link header__link--social"
						rel="noopener noreferrer"
					>
						<i class="far fa-lightbulb" />
					</a>
				</li>
				<li>
					<a
						href="/"
						target="_blank"
						class="header__link header__link--social"
						rel="noopener noreferrer"
					>
						<i class="far fa-save" />
					</a>
				</li>
				<li>
					<a
						href="/"
						target="_blank"
						class="header__link header__link--social"
						rel="noopener noreferrer"
					>
						<i class="far fa-user-circle" />
					</a>
				</li>
			</ul>
		</nav>
	</div>
</header>

<style>
	.header {
		margin-bottom: var(--spacing-1);
		background-color: var(--color-gray-medium-faded);
		border-bottom: 2px solid var(--color-gray-medium);
		text-align: center;

		@media (--mq-tablet-min) {
			margin-bottom: var(--spacing-2);
			text-align: left;
		}
	}

	.header__wrapper {
		justify-content: space-between;
		align-items: center;
		padding: var(--spacing-1) var(--spacing-n1);
		max-width: var(--container-max);
		margin: 0 auto;

		@media (--mq-tablet-min) {
			padding: var(--spacing-1) var(--spacing-2);
			display: flex;
		}
	}

	.header__title {
		font-size: var(--font-size-medium);
	}

	.header__subtitle {
		font-size: var(--font-size-small);
		color: var(--color-gray-light);
		padding: var(--spacing-n1) 0;

		@media (--mq-tablet-min) {
			padding: var(--spacing-n4) 0 0 0;
		}
	}

	.header__link {
		display: block;
		text-decoration: none;
		color: var(--color-gray-light);
		margin: 0;
	}

	.header__link--title {
		color: var(--color-primary);
	}

	.header__link--title:hover {
		color: var(--color-primary-tint);
	}

	.header__list {
		display: flex;
		list-style: none;
		padding: 0;
		justify-content: center;

		@media (--mq-tablet-min) {
			justify-content: flex-end;
		}
	}

	.header__list > li + li {
		margin-left: var(--spacing-n1);
	}

	.header__link--subtitle {
		display: inline-block;
		text-decoration: underline;
	}

	.header__link--subtitle:hover {
		color: var(--color-secondary-tint);
	}

	.header__link--page {
		color: var(--color-secondary);
		background-color: var(--color-secondary-faded);
		border: 2px solid currentColor;
		padding: var(--spacing-n2) var(--spacing-1);
		font-family: var(--font-family-primary);
		border-radius: var(--spacing-n2);
	}

	.header__link--page:hover,
	.header__link--page:active,
	.header__link--page:focus {
		box-shadow: 0 0 2px 1px var(--color-secondary);
	}

	.header__link--social {
		background-color: var(--color-gray-medium-faded);
		border: 2px solid currentColor;
		padding: var(--spacing-n2) var(--spacing-n1);
		font-family: var(--font-family-primary);
		border-radius: var(--spacing-n2);
	}

	.header__link--social:hover,
	.header__link--social:active,
	.header__link--social:focus {
		box-shadow: 0 0 2px 1px var(--color-gray-light);
	}

	.header__subtitle--ready {
		animation: fadeIn 0.5s ease forwards 1;
	}

	@keyframes fadeIn {
		from {
			opacity: 0;
		}
		to {
			opacity: 1;
		}
	}
</style>
