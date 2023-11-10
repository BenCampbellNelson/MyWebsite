<div class="page-inner">
	<div class="card">
		<div class="content">
			<div class="image">
				<img src="images/justinRoiland.webp" alt="Justin Roiland" />
			</div>
			<div class="text">
				<h2>Mark Justin Roiland</h2>
				<p>
					Mark Justin Roiland is a writer, animator, director, producer, and the co-creator of the
					popular show "Rick and Morty." He provided the voices for Rick and Morty from Season 1 to
					Season 6. However, as of January 24, 2023, he has been dismissed from the series amid
					charges of domestic abuse. His voice roles will be recast with soundalike actors starting
					with Season 7. It's important to note that following his firing, the charges were
					dismissed due to insufficient evidence, but allegations of sexual assault were reported
					against him.
				</p>
			</div>
		</div>
	</div>

	<div class="card">
		<div class="content">
			<div class="text">
				<h2>Dan Harmon</h2>
				<p>
					Dan Harmon is a writer, producer, actor, and the co-creator of "Rick and Morty." He has
					also served as an executive producer for the series. As of January 24, 2023, he is the
					sole showrunner of the series. This decision was made by Adult Swim after severing ties
					with co-creator Justin Roiland, who was fired from the series amid charges of domestic
					abuse.
				</p>
			</div>
			<div class="image">
				<img src="images/Dan_Harmon1.webp" alt="Dan Harmon" />
			</div>
		</div>
	</div>

	<div class="card">
		<div class="content">
			<div class="image">
				<img src="images/Ian_Cardoni.webp" alt="Ian Cardoni" />
			</div>
			<div class="text">
				<h2>Ian Cardoni</h2>
				<p>
					Ian Cardoni is a versatile and accomplished actor and comedian known for his exceptional
					talent and charismatic presence. His career spans various creative endeavors, showcasing
					his ability to captivate audiences through his unique blend of humor and storytelling. One
					of Ian Cardoni's notable contributions is his involvement in the popular animated TV
					series, "Rick and Morty." He has lent his voice to several memorable characters, adding
					depth and humor to the show's dynamic cast. Ian's comedic prowess and vocal versatility
					have made his characters in "Rick and Morty" stand out, leaving a lasting impression on
					fans worldwide. Ian Cardoni's work on "Rick and Morty" exemplifies his ability to bring
					humor and authenticity to animated characters, contributing to the show's success and
					cementing his reputation as a talented performer in the world of voice acting and comedy.
					His unique talent continues to shine in the entertainment industry, making him a valuable
					asset to any project he's a part of. Ian Cardoni is a talented voice actor in the animated
					series "Rick and Morty," where he has brought life to some memorable characters. Notably,
					he voices characters like "Abradolf Lincler" and "Shnoopy Bloopers." These characters have
					become fan favorites for their quirky and humorous personalities. Abradolf Lincler is a
					fusion of Abraham Lincoln and Adolf Hitler, creating a hilariously conflicted character
					who struggles with his dual identity. Shnoopy Bloopers, on the other hand, is a character
					known for his bizarre and comical interactions in the series. Ian Cardoni's contributions
					to these characters have added an extra layer of humor and depth to "Rick and Morty,"
					making his voice work an integral part of the show's charm and appeal. His ability to
					embody such unique and entertaining characters has endeared him to fans of the series.
				</p>
			</div>
		</div>
	</div>

</div>

<style>
	.card {
		display: flex;
		border: 2px solid #000;
		border-radius: 10px;
		margin: 20px;
		padding: 20px;
		background-color: #b7e4f999;
	}

	.content {
		display: flex;
		flex: 1;
		min-height: 0;
	}

	.image {
		display: flex;
		flex: 1;
	}

	.image img {
		max-width: 100%;
		max-height: 100%;
		border-radius: 10px;
	}

	.text {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 20px;
		font-family: var(--main-font-family);
	}

	h2 {
		font-size: 24px;
		color: white;
	}

	p {
		font-size: 2em;
		color: white;
	}

	@media (max-width: 800px) {
		.content {
			flex-direction: column;
		}

		.text {
			flex: auto; /* This will allow the text container to expand as needed */
		}

		.image img {
			max-width: 100%; /* Allow the image to adjust to its parent's width */
			max-height: 100%; /* Adjust the maximum height as needed */
			border-radius: 10px;
		}

		.image {
			height: 200px;
			width: 100px;
		}
	}
</style>
