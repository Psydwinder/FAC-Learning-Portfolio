# HTTP portfolio


## 1. Write code that executes asynchronously
<details>
  <summary>Evidence</summary>
</details>

## 2. Use callbacks to access values that aren't available asynchronously 
<details>
  <summary>Evidence</summary>
  <br>
  I used the showMovies() callback function using the data gathered from the async function getMovies() in order to get values such as the title, poster image (poster_path), film's average score (vote_average), film description (overview) and the film id. The values would then be rendered on the page inside an individual movie card.
  
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
  </details>

## 4. Use the fetch method to make the HTTP requests and receive responses
<details>
  <summary>Evidence</summary>
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
  </details>
  
## 9. Add and remove DOM nodes to change the content on the page
<details>
  <summary>Evidence</summary>
  </details>

## 10. Toggle the classes applied to DOM nodes to change their CSS properties
<details>
  <summary>Evidence</summary>
  </details>
  
## 11. Use consistent layout and spacing
<details>
  <summary>Evidence</summary>
  <br>
  With this project I tried to have a consistent look to the app, utilising CSS grids to space out the movie cards regardless of the device it was being dsiplayed on.
  
  |![image](https://user-images.githubusercontent.com/101563800/206185802-52e52a94-e8b7-482e-b32b-e59a75a6193c.png)|
  |:--:|
  |*Above: Consistent layout and spacing for the movie cards*|
  </details>

## 12. Follow a spacing guideline to give our app a consistent feel
<details>
  <summary>Evidence</summary>
  </details>
  
## 13. Debug client side JS in our web browser
<details>
  <summary>Evidence</summary>
  </details>
  
## 14. Use console.log() to help us debug our code
<details>
  <summary>Evidence</summary>
  </details>
