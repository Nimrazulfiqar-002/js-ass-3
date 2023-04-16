# js-ass-3
assignment 3
//html
<!DOCTYPE html>
<html>
<head>
	<title>Movie Recommendation App</title>
	<link rel="stylesheet" type="text/css" href="./css3.css">
    <script src="./app.js"></script>
</head>
<body>
    <header>
        <h1>Movie Recommendation App</h1>
        <div class="search-form-container">
          <input
            id="searchInput"
            type="text"
            placeholder="Search for movies..."
          />
          <button id="searchBtn">Search</button>
        </div>
      </header>
     <main>	
        <div class="container">
		<label for="genre" > Genre</label>

		<select id="genre" >
            <option value="All">All</option>
			<option value="action">Action</option>
			<option value="comedy">Comedy</option>
			<option value="drama">Drama</option>
			<option value="horror">Horror</option>
			
		</select>
		<br><br>
		<label for="year">Year</label>
		<select id="year">
            <option value="">All</option>
			<option value="2022">2022</option>
			<option value="2021">2021</option>
			<option value="2020">2020</option>
			<option value="2019">2019</option>
		
			<option value="2017">2017</option>
		</select>
		<br><br>
        <label for="Ranting">Ranting</label>
		<select id="rank">
            <option value="">All</option>
			<option value="1">1</option>
			<option value="2">2</option>
			<option value="3">3</option>
			<option value="4">5</option>
		
		
		</select>
		<br><br>
        <label for="Language">Language</label>
		<select id="Language">
            <option value="">All</option>
			<option value="2022">Eng</option>
			<option value="2021">french</option>
		
		</select>
		<br><br>
       <section id="movie result">
		<div id="movie-list"></div>
        
	<script src="./app.js"></script>
	</div>
</section>
</main>


</body>
</html> 

//CSS
*{
    padding: 0%;
    margin: 0%;
    box-sizing:border-box ;
}
html{
    font-size: 50%;
}
body{
    font-family: 'Times New Roman', Times, serif;
}
.container {
	max-width: 500px;
	margin: auto;
	/* text-align: right; */
    column-count: 4;
}

h1 {
	font-size: 40px;
	margin-bottom: 10px;
}

label {
	font-size: 10px;
	margin-right: 7px;
    column-count: 4;
}

select {
	font-size: 8px;
	padding: 5px;
	margin-bottom: 20px;
}

 button {
	font-size: 12px;
    size:10px;
	/* padding: 10px 20px; */
	background-color: #4CAF50;
	color: white;
	border: none;
	border-radius: 2px;
	cursor: pointer;
  margin-left: 1px;
  margin-right: 1px;
}

button:hover {
	background-color: #3e8e41;
} 


//js
(async function(){
    const response=await fetch("./data.json");
    const movies=await response.json();
  

  const inputElem = document.getElementById("searchInput");
  const btnElem = document.getElementById("searchBtn");
//   const listElem = document.getElementById("recipe-list");
//   const detailsElem = document.getElementById("recipeDetailsContainer");
function search(){
    const query = inputElem.value;
}
btnElem.addEventListener(click, () => {
    // Get user's selected genre and year
    const selectedGenre = document.getElementById("genre").value;
    const selectedYear = document.getElementById("year").value;
    
    // Filter movies based on user's selections
    const recommendedMovies = movies.filter(movie => movies.genre === Genre && movies.year == Year);
    
    // Clear the movie list
    movieList.innerHTML = "";
  return movies.tittle.toLowerCase().includes(query);
// Display recommended movies
recommendedMovies.forEach(movie => {
    // Create movie card
    const movieCard = document.createElement("div");
    movieCard.classList.add("movie-card");
 
    // Create movie image
    const movieImg = document.createElement("img");
    movieImg.src = movie.image;
 
    // Create movie title
    const movieTitle = document.createElement("h2");
    movieTitle.textContent = movie.title;
 
    // Create movie description
    const movieDesc = document.createElement("p");
    movieDesc.textContent = `Genre: ${movie.genre} | Year: ${movie.year}`;
 
    // Add image, title, and description to movie card
    movieCard.appendChild(movieImg);
    movieCard.appendChild(movieTitle);
    movieCard.appendChild(movieDesc);
 
    // Add movie card to movie list
    movieList.appendChild(movieCard);

    [{title: "Joker",
genre: "drama",
year: 2019,
image: "https://www.themoviedb.org/t/p/w600_and_h900_bestv2/udDclJoHjfjb8Ekgsd4FDteOkCU.jpg"
},
{
title: "Knives Out",
genre: "comedy",
year: 2019,
image: "https://www.themoviedb.org/t/p/w600_and_h900_bestv2/qG59J1Q7rpBc1dvku4azbzcqo8h.jpg"
},
{
title: "Us",
genre: "horror",
year: 2019,
image: "https://www.themoviedb.org/t/p/w600_and_h900_bestv2/mvDVOYluQwcyfqTITJcT2gVesjP.jpg"
},
{
title: "The Notebook",
genre: "romance",
year: 2004,
image: "https://www.themoviedb.org/t/p/w600_and_h900_bestv2/k0oN89q8K1zll9OsHk5NWmHZZGI.jpg"
},
{
title: "Inception",
genre: "sci-fi",
year: 2010,
image: "https://www.themoviedb.org/t/p/w600_and_h900_bestv2/qmDpIHrmpJINaRKAfWQfftjCdyi.jpg"
},
];



};
}
)();
