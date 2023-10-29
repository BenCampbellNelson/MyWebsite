<script>
	let character_total = 0;
	let character = [];
	let guessInput = ''; // Added variable to store the input field value
	let score = 0; //add score variable
	let characterNameHints = '';

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
			// Display an incorrect guess message
			messageElement.textContent = 'Incorrect guess, please try again.';
			messageElement.style.display = 'block';

			// Hide the message after a few seconds (e.g., 3 seconds)
			setTimeout(() => {
				messageElement.style.display = 'none';
			}, 3000);

			guessInput = '';
			clearScore();
		}
	}

	fetchRandomCharacter();
</script>

<div class="pageContainer">
	<div class="characterGuess">
		<img class="characterImage" src={character.image} alt="characterImage" />
		<h1>{character.name}</h1>
        <h1>{characterNameHints}</h1>
		<form on:submit={checkGuess}>
			<label>
				Guess the character's name:
				<input type="text" name="characterName" bind:value={guessInput} />
			</label>
			<button type="submit">Submit Guess</button>
		</form>
		<div class="score">Score: {score}</div>
		<div id="message" style="display: none;" />
	</div>
</div>

<style>
	.characterGuess {
		display: flex;
		flex-direction: column;
		align-items: center;
		font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
		font-weight: 500;
		text-transform: uppercase;
	}
	.pageContainer {
		display: flex;
		justify-content: center;
	}

	.characterImage {
		width: 20vw;
		height: 20vw;
		border-radius: 20px;
	}
</style>
