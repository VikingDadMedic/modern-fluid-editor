<footer class="footer">

	<p class="footer__section">
		Created with <i class="fa-solid fa-heart footer__icon" /> and
		<i class="fa-solid fa-fire footer__icon" />
		by
		<a
			class="footer__link footer__link--secondary"
			href="/"
			target="_blank"
			rel="noopener noreferrer"
		>
			ARQITEQT
		</a>
	</p>
</footer>

<style>
	.footer {
		text-align: center;
		padding: var(--spacing-2) var(--spacing-n1);
		background-color: var(--color-gray-medium-faded);
		border-top: 2px solid var(--color-gray-medium);
		font-weight: var(--font-weight-bold);

		@media (--mq-tablet-min) {
			padding: var(--spacing-2);
		}
	}

	.footer__link {
		text-decoration: none;
		font-family: var(--font-family-primary);
	}

	.footer__link:hover,
	.footer__link:active {
		text-decoration: underline;
	}

	.footer__link--primary {
		color: var(--color-primary);
	}

	.footer__link--secondary {
		color: var(--color-secondary);
	}

	.footer__section + .footer__section {
		margin-top: var(--spacing-1);
	}

	.footer__link--social {
		display: flex;
		align-items: center;
		text-align: center;
		justify-content: center;
		color: var(--color-gray-light);
		background-color: var(--color-gray-medium-faded);
		border: 2px solid currentColor;
		width: calc(var(--spacing-1) + var(--spacing-n1));
		aspect-ratio: 1;
		font-family: var(--font-family-primary);
		border-radius: var(--spacing-n2);
	}

	.footer__link--social:hover,
	.footer__link--social:active,
	.footer__link--social:focus {
		box-shadow: 0 0 2px 1px var(--color-gray-light);
		text-decoration: none;
	}

	.footer__links {
		list-style: none;
		padding: 0;
		display: flex;
		justify-content: center;
		margin-top: var(--spacing-1);
	}

	.footer__item + .footer__item {
		margin-left: var(--spacing-n1);
	}
</style>
