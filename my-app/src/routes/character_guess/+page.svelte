<!--JAVASCRIPT-->
<script>
	let character_total = 0;
	let character = [];
	let guessInput = '';
	let score = 0;
	let characterNameHints = '';
	let showHints = false;

	const BASE_URL = 'https://rickandmortyapi.com';

	function fetchRandomCharacter() {
		fetch(BASE_URL + '/api/character')
			.then((res) => res.json())
			.then((data) => {
				character_total = data.info.count;
				console.log(data);

				let character_id = [];

				character_id = Math.floor(Math.random() * character_total);

				console.log(character);

				fetch(`${BASE_URL}/api/character/${character_id}`)
					.then((res) => res.json())
					.then((data2) => {
						character = data2;
						console.log(character);
						generateNameHints();
					});
			});

		showHints = false;
	}

	function generateNameHints() {
		const name = character.name;
		let hint = '';

		for (let i = 0; i < name.length; i++) {
			// Check if the character is a special character
			const isSpecialCharacter = /[+\\-\\' ']/.test(name[i]);

			// Replace only regular characters with underscores randomly
			hint += isSpecialCharacter || Math.random() < 0.5 ? name[i] : '_';

			if (i < name.length - 1) {
				hint += ' ';
			}
		}
		characterNameHints = hint;
	}

	function toggleHints() {
		showHints = !showHints;

		if (showHints) {
			generateNameHints(); // Generate hints if showHints is true
		} else {
			characterNameHints = '';
		}
	}

	function updateScore() {
		score++;
	}

	function clearScore() {
		score = 0;
	}

	function scoreMinus() {
		if (score >= 1) {
			score--;
		}
	}

	function checkGuess(event) {
		event.preventDefault();
		const guess = event.target.querySelector('input[name="characterName"]').value;
		const messageElement = document.getElementById('message');

		if (character.name.toLowerCase() === guess.toLowerCase()) {
			messageElement.textContent = 'Correct!';
			messageElement.style.display = 'block';

			// Hide the message after a few seconds (e.g., 3 seconds)
			setTimeout(() => {
				messageElement.style.display = 'none';
			}, 3000);
			fetchRandomCharacter();
			guessInput = ''; // Reset the input field value
			updateScore();
		} else {
			messageElement.textContent = 'Incorrect guess, please try again.';
			messageElement.style.display = 'block';

			setTimeout(() => {
				messageElement.style.display = 'none';
			}, 3000);

			guessInput = '';
			clearScore();
		}
	}

	fetchRandomCharacter();
</script>

<!--HTML-->
<div class="pageContainer">
	<div class="characterGuess">
		<img class="characterImage" src={character.image} alt="characterImage" />
		<form on:submit={checkGuess}>
			<label class="input">
				Guess the character's name:
				<input
					type="text"
					name="characterName"
					bind:value={guessInput}
					style="width: 100%; font-size: 1em; border-radius: 50px;"
				/>
			</label>
			<div class="buttons">
				<button
					class="skip-button"
					on:click={() => {
						scoreMinus();
						fetchRandomCharacter();
					}}>Skip to Next Character (-1 point)</button
				>
				<button
					class="hint-button"
					on:click={() => {
						scoreMinus();
						toggleHints();
					}}>Show Hint (-1 point)</button
				>
				<button type="submit">Submit Guess</button>
			</div>
		</form>
		<div class="score">Score: {score}</div>
		<div id="message" style="display: none;" />
		<div class="hint">
			{#if showHints}
				<h1>{characterNameHints}</h1>
			{/if}
		</div>
	</div>
</div>

<!--CSS-->
<style>
	.buttons {
		display: flex;
	}
	button:active {
		box-shadow: none;
		transform: translate(3px, 3px);
	}

	button:hover {
		background: #FF5F1F;
	}

	.hint-button,
	form button[type='submit'],
	.skip-button {
		font-family: var(--main-font-family);
		font-size: 1.5rem;
		color: #fafafa;
		text-transform: uppercase;
		padding: 10px 20px;
		border-radius: 10px;
		border: 2px solid #fafafa;
		background: #252525;
		box-shadow: 3px 3px #fafafa;
		cursor: pointer;
		margin: 35px 0;
	}

	.input {
		display: flex;
		flex-direction: column;
	}
	.characterGuess {
		display: flex;
		flex-direction: column;
		align-items: center;
		font-family: var(--main-font-family);
		font-weight: 500;
		text-transform: uppercase;
		font-size: 2vw;
		color: white;
	}

	.characterGuess form {
		display: flex;
		flex-direction: column;
	}
	.pageContainer {
		display: flex;
		justify-content: center;
	}

	.characterImage {
		max-width: 100%;
		height: auto;
		border-radius: 20px;
		margin: 20px;
	}

	@media (max-width: 800px) {
		.characterGuess {
			font-size: 5vw;
		}

		.hint-button,
		form button[type='submit'],
		.skip-button {
			font-size: 0.7rem;
		}
	}
</style>
