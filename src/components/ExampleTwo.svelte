<script>
    let firstName = "";
    let lastName = "";
    let gender = "";
    let favColor = "";

    $: fullName = `${firstName} ${lastName}`; // simplified reactive variable
</script>

<div class="container">
    <div class="code">
        <label>First Name</label>
        <input type="text" bind:value={firstName}>
        <label>Last Name</label>
        <input type="text" bind:value={lastName}>

        <label>Gender</label>
        <select bind:value={gender}>
            <option value=""></option>
            <option value="male">Male</option>
            <option value="female">Female</option>
        </select>

        <label>Favorite Color</label>
        <input type="text" bind:value={favColor}>

        <h3>My name is {fullName}, a {gender} and my favorite color is <span style="color: {favColor}">{favColor}</span>.</h3>

    </div>
    <div class="output">
        {`<script>`}<br>
        <span class="span-ml">{`let firstName = "";`}<br></span> 
        <span class="span-ml">{`let lastName = "";`}<br></span> 
        <span class="span-ml">{`let gender = "";`}<br></span>
        <span class="span-ml">{`let favColor = "";`}<br><br></span>

        <span class="span-ml">{'$:fullName ='} {'`${firstName} ${lastName}`'}<br></span>
        {`</script>`}<br><br>

        {`<label>First Name</label>`}<br>
        {`<input type="text" bind:value={firstName}>`}<br><br>
        {`<label>Last Name</label>`}<br>
        {`<input type="text" bind:value={lastName}>`}<br><br>
        {`<label>Gender</label>`}<br>
        {`<select bind:value={gender}>`}<br>
        <span class="span-ml">{`<option value=""></option>`}<br></span>
        <span class="span-ml">{`<option value="male">Male</option>`}<br></span>
        <span class="span-ml">{`<option value="female">Female</option>`}<br></span>
        {`</select>`}<br><br>
        {`<label>Favorite Color</label>`}<br>
        {`<input type="text" bind:value={favColor}>`}<br><br>
        {`<h3>My name is {fullName}, a {gender} and my favorite color is <span style="color: {favColor}">{favColor}</span>.</h3>`} 
    </div>
</div>