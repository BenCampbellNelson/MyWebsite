<script>

    let character_total = 0;

    const BASE_URL = "https://rickandmortyapi.com"

    fetch(BASE_URL + "/api/character")
    .then((res) => res.json())
    .then((data) => {

        character_total = data.info.count
        console.log(character_total)
    })
</script>
