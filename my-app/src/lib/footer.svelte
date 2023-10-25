

<div class ="footer">
    <h1>this is the footer</h1>
    <div class="footerNav">
        <ul class="nav_list">
			<li class="nav_item">
				<a class="nav_link" href="/">HOME</a>
			</li>
			<li class="nav_item">
				<a class="nav_link"  href="/trivia">TRIVIA</a>
			</li>
			<li class="nav_item">
				<a class="nav_link" href="/character_guess">CHARACTER GUESS</a>
			</li>
			<li class="nav_item">
				<a class="nav_link" href="/episode_guess">EPISODE GUESS</a>
			</li>
    </div>
    <div class ="socialMedia">
        social
    </div>
    <div class = "copyRight">
        copyright
    </div>
</div>


<style>
    .footer{
        display: flex;
        margin-top: auto;
        flex-direction: column;
        background-color: var(--main-colour);
        color: white;
        align-items: center;
    }

    .nav_list{
        list-style: none;
        display: flex;
        flex-direction: row;
    }

    .nav_item a{
        text-decoration: none;
        color: inherit;
        padding: 5px;
    }
</style>
