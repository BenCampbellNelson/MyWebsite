<script>
	let character_total = 0;
	let character = [];
	let guessInput = ''; // Added variable to store the input field value
	let score = 0; //add score variable
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
	}

	function generateNameHints() {
		const name = character.name;
		let hint = '';

		for (let i = 0; i < name.length; i++) {
			// Check if the character is a special character
			const isSpecialCharacter = /[+\\-\\' ']/.test(name[i]);

			// Replace only regular characters with underscores randomly
			hint += isSpecialCharacter || Math.random() < 0.5 ? name[i] : '_';
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

	function skipToNextCharacter() {
        if (score >= 1)
        {
            score--;
        }
		fetchRandomCharacter(); // Fetch a new random character
		guessInput = ''; // Reset the input field value
	}
</script>

<div class="pageContainer">
	<div class="characterGuess">
		<img class="characterImage" src={character.image} alt="characterImage" />
		<button class="skip-button" on:click={skipToNextCharacter}>Skip to Next Character (-1 point)</button>
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
			<button type="submit">Submit Guess</button>
		</form>
		<div class="score">Score: {score}</div>
		<div id="message" style="display: none;" />
		<button class="hint-button" on:click={toggleHints}>Show Hints</button>
		<div class="hint">
			{#if showHints}
				<h1>{characterNameHints}</h1>
			{/if}
		</div>
	</div>
</div>

<style>
	.hint {
	}

    .input{
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
	}

	.hint-button,
	form button[type='submit'], .skip-button {
		background-color: #007bff;
		color: white;
		border: none;
		padding: 2% 4%;
		margin: 10px;
		cursor: pointer;
		border-radius: 50px;
        text-transform: uppercase;
        font-weight: 500;
	}

	@media (max-width: 800px) {
		.characterGuess {
			font-size: 3vw; 
		}
	}
</style>
