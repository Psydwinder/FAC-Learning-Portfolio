# HTTP portfolio


## 1. Write code that executes asynchronously
<details>
  <summary>Evidence</summary>
  <br>
  JavaScript is a “single-threaded” language. This means things generally happen one at a time, in the order you wrote the code. When something needs to happen out of this order, we call it “asynchronous” (“async” for short). JavaScript handles this using a “queue”. Anything async gets pushed out of the main running order and into the queue. Once JS finishes what it was doing it moves on to the first thing in the queue.
  
  
  |![Async explanation](http://mariechatfield.com/tutorials/assets/async/diagram_async_02.png)|
  |:--:|
  |*Above: Async Function diagram explanation*|
  
  <br>
  
  By using the fetch API method I was able to write code that executes asynchronously. You can view the entire project and code [**here**](https://github.com/fac26/CatsDogsOrMovies)
  
  
</details>

## 2. Use callbacks to access values that aren't available asynchronously 
<details>
  <summary>Evidence</summary>
  <br>
  I used the showMovies() callback function within the async function getMovies(). With the purpose of this function being that it accesses the title, poster_path(the poster image), vote_average (The user score for that movie based on people rating it between 0 and 10), overview (the movie description) and the ID.
  
  
  You can seen an example of this below:
  
  
  ```JS
  function showMovies(data) {
  main.innerHTML = "";
  data.forEach((movie) => {
    const { title, poster_path, vote_average, overview, id } = movie;
    const movieEl = document.createElement("div");
    movieEl.classList.add("movie");
  ```
</details>

## 3. Use promises to access values that aren't available asynchronously
<details>
  <summary>Evidence</summary>
  <br>
  From the below code snippet you can see that we must first fetch some data from a server. It takes two arguments: the URL you want to send the request to and an options object.  From this we will receive a promise that will eventually represent the server’s response (when the network request completes).
 
  
  We must then access the promises value. Since the API returns JSON-formatted data we can use the response.json() method, shortened to res.json() here, to access it. The .json() method also returns a promise, so we need to use another .then() to access the value.
  
  
  In the end we can log the values we get from the response in the form of data with the line console.log(data.results)
  
  
  ```JS
  function getMovies(url) {
  lastUrl = url;
  fetch(url)
    .then((res) => res.json())
    .then((data) => {
      console.log(data.results);
  ```
  </details>

## 4. Use the fetch method to make the HTTP requests and receive responses
<details>
  <summary>Evidence</summary>
  <br>
  Similar to evidence #3
  
   From the below code snippet you can see that we must first fetch some data from a server. It takes two arguments: the URL you want to send the request to and an options object.  From this we will receive a promise that will eventually represent the server’s response (when the network request completes).
 
  We must then access the promises value. Since the API returns JSON-formatted data we can use the response.json() method, shortened to res.json() here, to access it. The .json() method also returns a promise, so we need to use another .then() to access the value.
  
  In the end we can log the values we get from the response in the form of data with the line console.log(data.results)
  
  ```JS
  function getMovies(url) {
  lastUrl = url;
  fetch(url)
    .then((res) => res.json())
    .then((data) => {
      console.log(data.results);
  ```
  </details>

## 5. Configure the options argument of the fetch method to make GET and POST requests
<details>
  <summary>Evidence</summary>
  </details>
  
## 6. Use the map array method to create a new array containing new values
<details>
  <summary>Evidence</summary>
  </details>
  
## 7. Use the filter array method to create a new array with certain values removed
<details>
  <summary>Evidence</summary>
  </details>

## 8. Access DOM nodes using a variety of selectors
<details>
  <summary>Evidence</summary>
  <br>
  I have used various selectors throughout this project. You can see an example of this in the code snippet below.
  
  ```JS
  const main = document.getElementById("main");
const form = document.getElementById("form");
const search = document.getElementById("search");
const tagsEl = document.getElementById("tags");
const hamburger = document.getElementById("hamburger");
const navMenu = document.getElementById("nav-menu");
const prev = document.getElementById("previous");
const next = document.getElementById("next");
const current = document.getElementById("current");
  ```
  
  </details>
  
## 9. Add and remove DOM nodes to change the content on the page
<details>
  <summary>Evidence</summary>
  <br>
  
  For this project I wanted to be able to create "movie cards" dynamically, so that as the TMDB API was updated so to would the displayed movies on the app. Below is code snippet for the showMovies() function that creates a div element with the class movie. Within this element the title, the film description, the film poster and average user score can be filled in from the data that is fetched from the TMDB API. 
  
  ```JS
  function showMovies(data) {
  main.innerHTML = "";
  data.forEach((movie) => {
    const { title, poster_path, vote_average, overview, id } = movie;
    const movieEl = document.createElement("div");
    movieEl.classList.add("movie");
    movieEl.innerHTML = `
    <img src="${
      movie.poster_path
        ? IMAGE_URL + movie.poster_path
        : "https://www.cinemahalls.com/wp-content/uploads/2019/10/Picture-Not-Available-1.jpg"
    }"
    alt="${title} image"
  />
  <div class="movie-info">
    <h3>${title}</h3>
    <span class="${getColor(vote_average)}">${vote_average}</span>
  </div>
  <div class="overview">
    <h3>${title}</h3>
    ${overview}
    <br />
    <button class="watch-trailer" id="${id}">Watch trailer</button>
  </div>`;

    main.appendChild(movieEl);

    document.getElementById(id).addEventListener("click", () => {
      console.log(id);
      openNav(movie);
    });
  });
}
  ```
  </details>

## 10. Toggle the classes applied to DOM nodes to change their CSS properties
<details>
  <summary>Evidence</summary>
  <br> 
  Similar to some of my other projects, I have used the classList.add or classList.remove methods to change the css properties of various elements throughout this project. 
  
  An example of this can be seen below:
  
  ```JS
  current.innerText = currentPage;
        if (currentPage <= 1) {
          prev.classList.add("disabled");
          next.classList.remove("disabled");
        } else if (currentPage >= totalPages) {
          prev.classList.remove("disabled");
          next.classList.add("disabled");
        } else {
          prev.classList.remove("disabled");
          next.classList.remove("disabled");
        }
  ```
  
  Here the if else statement checks to see what page the user is currently on before doing one of three things: 
  
  
  1. If the user is on the first page **the previous button will be disabled** and **have settings applied to it** to show the user they cant click it.
  2. If the user is on the last page **the next button will be disabled** and **have settings applied to it** to show the user they cant click it.
  3. If the user isn't on the first page or last page **both the previous and next button will have the class "disabled" removed** and the test of the button will appear white indicating the user can go to the next or previous page.
  
  </details>
  
## 11. Use consistent layout and spacing
<details>
  <summary>Evidence</summary>
  <br>
  With this project I tried to have a consistent look to the app, utilising CSS grids to space out the movie cards regardless of the device it was being displayed on.
  
  |![image](https://user-images.githubusercontent.com/101563800/206185802-52e52a94-e8b7-482e-b32b-e59a75a6193c.png)|
  |:--:|
  |*Above: Consistent layout and spacing for the movie cards*|
  </details>
  
## 12. Follow a spacing guideline to give our app a consistent feel
<details>
  <summary>Evidence</summary>
  <br>
   The styling for the app seen in Evidence #11 was achieved with the code below:
  
  ```CS
  main {
  display: grid;
  grid-template-columns: auto auto auto auto;
  justify-content: center;
}

.movie {
  width: 425px;
  margin: 1rem;
  background-color: var(--secondary-color);
  box-shadow: 0 4px 5px rgba(0, 0, 0, 0.2);
  position: relative;
  overflow: hidden;
  border-radius: 3px;
}
  ```
  </details>
  
## 13. Debug client side JS in our web browser
<details>
  <summary>Evidence</summary>
  </details>
  
## 14. Use console.log() to help us debug our code
<details>
  <summary>Evidence</summary>
  <br>
  
  ```JS
  function getMovies(url) {
  lastUrl = url;
  fetch(url)
    .then((res) => res.json())
    .then((data) => {
      console.log(data.results);
  ```
  I have used the console.log() method here to check that the data is being fetched and loaded from the TMDB API. This would be useful when creating a function that could check to see if the TMDB server is available and throw out an error if it isn't.
  
  </details>
