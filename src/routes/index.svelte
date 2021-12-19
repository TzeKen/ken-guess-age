<script>
    let user_name ="";
    let age ="";

    async function getAge() {
        fetch(' https://api.agify.io/?name=' + user_name)
        .then((response) => response.json())
        .then((data) => {
  	       user_name = data.name;
  	       age = data.age; 
	    });
    }
</script>

<form on:submit|preventDefault={getAge}>
    <label for="name">Name:</label>
    <input id="user_name" bind:value={user_name} type="text" />
    <button type="submit">Check</button>
</form>