<script>
    
	let character_total = 0;
	let character = [];

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
					});
			});
	}

    function checkGuess(event) {
        event.preventDefault();
        const guess = event.target.querySelector('input[name="characterName"]').value;
        if (character.name.toLowerCase() === guess.toLowerCase()) {
            
            fetchRandomCharacter();
        } else {
            
            alert("Incorrect guess, please try again.");
        }
    }

	fetchRandomCharacter();
</script>

<h1>{character.name}</h1>
<img src={character.image} alt="characterImage" />
<form on:submit={checkGuess}>
	<label>
		Guess the character's name:
		<input type="text" name="characterName" />
	</label>
    <button type ="submit">Submit Guess</button>
</form>