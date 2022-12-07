# HTTP portfolio


## 1. Write code that executes asynchronously
<details>
  <summary>Evidence</summary>
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
