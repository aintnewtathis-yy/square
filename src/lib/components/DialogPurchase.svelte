<script>
	import Tinkoff from './Tinkoff.svelte';

	let dialog;
</script>

<button
	class="btn-main"
	on:click={() => {
		dialog.showModal();
	}}
>
	Полная расшифровка
</button>

<dialog class="purchase-dialog" bind:this={dialog}>
	<div class="purchase-dialog__body">
		<h3>Купить полный разбор матрица "Квадрат Пифагора"</h3>
		<h4>стоимость - 780 рублей</h4>
		<p>
			Вы можете приобрести полную расшифровку своей психоматрицы навсегда!
		</p>

		<Tinkoff />
		<div class="icons">
			<img src="/sbp.svg" alt="purchase way" />
			<img src="/sberpay.svg" alt="purchase way" />
			<img src="/tink.svg" alt="purchase way" />
		</div>
		<button
			class="dialog-close"
			on:click={() => {
				dialog.close();
			}}
		>
			<img src="/x.svg" alt="cross icon" />
		</button>
	</div>
</dialog>

<style lang="scss">
	.purchase-dialog {
		margin: auto;
		max-width: 1100px;
		position: fixed;
		margin: auto;

		@include mobile{
			margin: auto 10px;
		}

		border-radius: var(--border-radius);

		&::backdrop {
			background: #000;
			filter: blur(2px);
			backdrop-filter: blur(2px);
			opacity: 0.25;
		}
		&__body {
			margin: 10px;
			padding: 30px;
			border-radius: var(--border-radius);
			background-color: #fff;
			display: flex;
			flex-direction: column;
			gap: 20px;

			@include mobile {
				padding: 20px;
			}

			h3 {
				font-family: Manege;

				@include fluid-text(55, 45);

				@include mobile {
					@include fluid-text(45, 30);

				}
			}
			h4 {
				font-family: Manege;

				@include fluid-text(25, 20);
			}

			p {
				padding-top: 20px;
				padding-bottom: 80px;
			}

			.icons {
				display: flex;
				gap: 15px;

				img {
					height: 22px;
					width: fit-content;
				}
			}

			.dialog-close {
				position: absolute;
				top: 25px;
				right: 25px;

				@include mobile {
					top: 10px;
					right: 10px;
				}
			}
		}
	}
</style>
