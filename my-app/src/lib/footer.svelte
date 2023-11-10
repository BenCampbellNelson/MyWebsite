

<div class ="footer">
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
        background-color: #B7E4F999;
        color: white;
        align-items: center;
        font-size: 1vw;
        font-family: var(--main-font-family);
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

    @media (max-width: 800px) {
    .footer {
        font-size: 3vw; 
    }

}
</style>
