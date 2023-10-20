<script>

    let character_total = 0;
    let character = [];
    

    const BASE_URL = "https://rickandmortyapi.com"

    fetch(BASE_URL + "/api/character")
    .then((res) => res.json())
    .then((data) => {

        character_total = data.info.count
        
        let character_id = [];

        character_id = Math.floor(Math.random() * character_total);

        console.log(character);

        fetch(`${BASE_URL}/api/character/${character_id}`)
        .then((res) => res.json())
        .then((data2) => {
            character = data2;
            console.log(character);
        })
    })
</script>
