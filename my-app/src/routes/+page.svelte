
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
                charges of domestic abuse. His voice roles will be recast with soundalike actors starting with
                Season 7. It's important to note that following his firing, the charges were dismissed due
                to insufficient evidence, but allegations of sexual assault were reported against him.
            </p>
        </div>
    </div>
</div>

<div class="card">
    <div class="content">
        <div class="text">
            <h2>Dan Harmon</h2>
            <p>
                Dan Harmon is a writer, producer, actor, and the co-creator of "Rick and Morty." He has also
                served as an executive producer for the series. As of January 24, 2023, he is the sole
                showrunner of the series. This decision was made by Adult Swim after severing ties with
                co-creator Justin Roiland, who was fired from the series amid charges of domestic abuse.
            </p>
        </div>
        <div class="image">
            <img src="images/Dan_Harmon1.webp" alt="Dan Harmon" />
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
        height: 500px;
        padding: 20px;
    }

    .content {
        display: flex;
        flex: 1;
    }

    .image {
        flex: 1;
    }

    .image img {
        max-width: 50%;
        max-height: 100%;
        border-radius: 10px;
    }

    .text {
        flex: 1;
        padding: 20px;
        font-family: var(--main-font-family);
    }

    h2 {
        font-size: 24px;
        color: white;
    }

    p {
        font-size: 16px;
        color: white;
    }

    @media (max-width: 800px) {

        .content{
            flex-direction: column;
        }
    }
</style>

