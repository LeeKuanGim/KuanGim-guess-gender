<script>
    let user_name="";
    let gender="";

    async function getGender() {
        fetch('https://api.genderize.io/?name=' + user_name)
            .then((response) => response.json())
            .then((data) => {
            user_name = data.name;
            gender = data.gender;
            });
        }
</script>
<h1>Guess Gender</h1>

<form on:submit|preventDefault={getGender}>
    <label for="name">Name:</label>
    <input id="user_name" bind:value={user_name} type="text" />
    <button type="submit">Check</button>
</form>
<p>Gender:{gender}</p>
