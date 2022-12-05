# Testing portfolio


## 1. Check that passing a given input into out tests returns the expected output
<details>
  <summary>Evidence</summary>
   
  One of the first tests I wrote was to test whether any text that is added into an input box can be added to the to do list. However, if the user was to try and add a task without entering any text within the input field they should be presented with an error message
  
  Below is the code snippet that demonstrates this:
  
  ```JS
  
  const testInput = document.getElementById("task-input");
  const testBtn = document.getElementById("addtaskbtn");
  const testList = document.getElementById("tasklist");
  const testItem = document.querySelectorAll(".task-item");

  function createTestTask(task) {
    testInput.value = task;
    testBtn.click();
    testInput.value = "";
  }

  function clearTest() {
    testList.innerHTML = "";
    localStorage.clear();
  }

  test("Test to see if there is an input within the input field", () => {
  createTestTask("");
  const error = document.querySelector("#errorMsg");
  error.classList.add("hidden");
  equal(
    error.textContent,
    "Please enter a task!",
    "Displayed error message for empty input"
  );
  clearTest();
});
  
  ```
  
  |![image](https://user-images.githubusercontent.com/101563800/205120928-41e99b00-c158-4514-9172-63e02252829d.png)|
  |:--:|
  |*Above: The test in action and running as intended*|

</details>

## 2. Write tests to mimic the behaviour of a user performing different actions
<details>
  <summary>Evidence</summary>
  
  Within our team we wrote various tests designed to mimic the behaviour of a real world user. 
  
  Below are some example in the console along with their code snippet counterparts:
  
  |![image](https://user-images.githubusercontent.com/101563800/205122126-63cd2a17-c63e-4629-b3af-ffb27f7e08b2.png)|
  |:--:|
  |*Above: Number error message test passed!|
  
  ``` JS
  test("Test to see if input is prevented when user only enters numbers", () => {
  createTestTask(1232131);
  const error = document.querySelector("#errorMsg");
  error.classList.add("hidden");
  equal(
    error.textContent,
    "Tasks should have some text, not just numbers.",
    "Displayed error message for empty input"
  );
  clearTest();
});
  ```
  
  |![image](https://user-images.githubusercontent.com/101563800/205122936-5e95e1af-caaf-4e23-a048-0c15bd8cbb30.png)|
  |:--:|
  |*Above: Error message test for an input longer than 30 characters passed!|
  
  ``` JS
 test("Test to see if input is prevented when user enters more than 30 characters", () => {
  createTestTask("abcdefghijklmnopqrstuwxyzabcedefghij");
  const error = document.querySelector("#errorMsg");
  error.classList.add("hidden");
  equal(
    error.textContent,
    "Please keep your task name under 30 characters.",
    "Displayed error message for empty input"
  );
  clearTest();
});
  ```
  
  |![image](https://user-images.githubusercontent.com/101563800/205123512-5c9190f3-7945-40ca-aa9b-b759a0716aff.png)|
  |:--:|
  |*Above: Deleting a task test passed!|
  
  ``` JS
  test("Clicking delete will remove a task from the list", () => {
  createTestTask("Task3");
  const trashBtns = document.querySelectorAll(".trash-btn");
  trashBtns[0].click();
  equal(trashBtns[0].offsetParent, null, "Task deleted from the list");
  });
  ```
  
</details>

## 3. Write testable, modular functions
<details>
  <summary>Evidence</summary>
  
  After having written the tests, following the RED, GREEN, REFACTOR principle from Test Driven Development I was able to write functions that related to the tests and would actually perform the task.
  
  Below is the code snippet that demonstrates this:
  
  ```JS
  function displayError() {
  error.textContent = "Please enter a task!";
  setTimeout(() => {
    error.textContent = "";
  }, 2000);
}
  ```
  </details>

## 4. Write functions that add, remove or modify DOM nodes
<details>
  <summary>Evidence</summary>
  <br>
  Below, are code snippets that allowed us to add, remove and modiy DOM nodes for various functions
  
  ```JS
 
  // ADD TASK
function addTask() {
  //Dynamically creating a new div for tasks and buttons to sit inside. This is what will be displayed when the button is clicked
  const taskDiv = document.createElement("div");
  taskDiv.classList.add("task");

  //Create list items
  const newTask = document.createElement("li");
  newTask.innerText = taskInput.value;
  newTask.classList.add("task-item");
  taskDiv.appendChild(newTask);

  //Add task to Local Storage
  saveLocalTasks(taskInput.value);
  //Check Mark button
  const completedButton = document.createElement("button");
  completedButton.innerHTML = '<i class="fas fa-check"></i>';
  completedButton.classList.add("complete-btn");
  taskDiv.appendChild(completedButton);

  //Delete button
  const trashButton = document.createElement("button");
  trashButton.innerHTML = '<i class="fas fa-trash"></i>';
  trashButton.classList.add("trash-btn");
  taskDiv.appendChild(trashButton);

  //Append to UL
  taskList.appendChild(taskDiv);

  //Clear Input value
  taskInput.value = "";
}
  ```
  
  The above code is the function for adding a task to the list. **It ADD's to the DOM node with the use of the appendChild() method.**
  
  ```JS
  
  function deleteCheck(e) {
  const item = e.target;

  //Delete task
  if (item.classList[0] === "trash-btn") {
    const todo = item.parentElement;
    removeLocalTodos(todo);
    todo.remove();
  }

  //Check Mark
  if (item.classList[0] === "complete-btn") {
    const todo = item.parentElement;
    todo.classList.toggle("completed");
  }
}
  
 ```
  
  The above code is for a function that performs two tasks 
  
  1. To delete a task from the task list as well from the local storage. **Demonstrating that it REMOVES's an element from the DOM node with the use of the remove() method.** 
  2. Toggling the class "completed" on element with ID todo. **Demonstrating that the DOM node is being modified with the use of the toggle() method.** 
  
  </details>

## 5. Apply event listeners to HTML form elements
<details>
  <summary>Evidence</summary>
  
  I have applied to event listeners to HTML form elements.
  
  This is demonstrated in the code below:
  
  In order to see how the everything links together we need to look through it sequentially.
  
  1. You need to decide which HTML form element you want to add an event listener to. In order to do this you need to look at the HTML file, recognise which element you want add an event listener to and make a note of the id/class of that element. In this case we are using the **button element with the ID addtaskbtn**
  
  ```HTML
  <form id="form">
      <div class="input-div">
        <input
          type="text"
          class="task-input"
          id="task-input"
          placeholder="Enter your task here"
          autocomplete="off"
        />
        <button
          name="add-task"
          type="submit"
          class="addtaskbtn"
          id="addtaskbtn"
        >
          <i class="fas fa-plus-square"></i>
        </button>
      </div>
      <div class="select">
        <select name="todos" class="filter-todo" id="filter-todo">
          <option value="all">All</option>
          <option value="completed">Completed</option>
          <option value="incomplete">Incomplete</option>
        </select>
      </div>
    </form>
  ```
  
  2. Next, you need to call that element in the JavaScript file using the **getElementById method**
  
  ```JS 
  const taskBtn = document.getElementById("addtaskbtn");
   ```
  
  3. Next, you create a function to perform a specific task. In this case the function is supposed to add a task into the task list and local storage.
  
  ```JS
  function addTask() {
  //Dynamically creating a new div for tasks and buttons to sit inside. This is what will be displayed when the button is clicked
  const taskDiv = document.createElement("div");
  taskDiv.classList.add("task");

  //Create list items
  const newTask = document.createElement("li");
  newTask.innerText = taskInput.value;
  newTask.classList.add("task-item");
  taskDiv.appendChild(newTask);

  //Add task to Local Storage
  saveLocalTasks(taskInput.value);
  //Check Mark button
  const completedButton = document.createElement("button");
  completedButton.innerHTML = '<i class="fas fa-check"></i>';
  completedButton.classList.add("complete-btn");
  taskDiv.appendChild(completedButton);

  //Delete button
  const trashButton = document.createElement("button");
  trashButton.innerHTML = '<i class="fas fa-trash"></i>';
  trashButton.classList.add("trash-btn");
  taskDiv.appendChild(trashButton);

  //Append to UL
  taskList.appendChild(taskDiv);

  //Clear Input value
  taskInput.value = "";
}

//Display error message
function displayError() {
  error.textContent = "Please enter a task!";
  setTimeout(() => {
    error.textContent = "";
  }, 2000);
}
  ```
  
  4. Next, you write a function that checks the validity of what has been entered in the input box to make sure it isn't empty, longer than 30 characters or only numeric. ** We call the previous function within this function as part of the else statement** because we only want to run this function if what has been entered in the input field is valid.**
  
  ```JS
  function validateTask(event) {
  event.preventDefault(); //Prevents page from refreshing when button is clicked

  if (taskInput.value.length == 0) {
    displayError();
    taskInput.focus();
    error.classList.remove("hidden");
  } else if (taskInput.value.length > 30) {
    errMsgMaxChar();
    taskInput.value = "";
    taskInput.focus();
    error.classList.remove("hidden");
  } else if (!isNaN(taskInput.value)) {
    errMsgNumInput();
    taskInput.focus();
    error.classList.remove("hidden");
  } else {
    return addTask();
  }
}
  ```
  
  5. Lastly, we add an event listener to the button element.
  
  ```JS
  taskBtn.addEventListener("click", validateTask);
  ```
  </details>
  
## 6. Use scope to control what variables are accessible inside functions and blocks
<details>
  <summary>Evidence</summary>
  
  I can demonstrate that I have used variables with a mixture of **global** and **local** scope.
  
  ```JS
  //Selectors
const taskInput = document.getElementById("task-input");
const taskBtn = document.getElementById("addtaskbtn");
const taskList = document.getElementById("tasklist");
const filterOption = document.querySelector(".filter-todo");
const form = document.getElementById("form");
const error = document.getElementById("errorMsg");
  ```
  
  The above code snippet are variables with **global scope** as they are used in multiple places throughout the code.
  
  ```JS
  const completedButton = document.createElement("button");
  completedButton.innerHTML = '<i class="fas fa-check"></i>';
  completedButton.classList.add("complete-btn");
  taskDiv.appendChild(completedButton);
  ```
  
  The completedButton variable above has **local scope** as it is isolated within the add task function.
  </details>
  
## 7. Use CSS grid to create complex layouts
<details>
  <summary>Evidence</summary>
  <br>
  
  Although we haven't used CSS Grids in this project. I have utilised it in other projects.
  
  Below is an example code snippet used within the HTTP Project
  
  ```CSS
  main {
  display: grid;
  grid-template-columns: auto auto auto;
  justify-content: center;
}
  ```
  |![image](https://user-images.githubusercontent.com/101563800/205526727-cd47adfb-6b64-4fa8-9ac2-533eaee6272d.png)|
  |:--:|
  |*Above: What the code looks like visually*|

  </details>

## 8. Use CSS grid to make layouts that adapt to the viewport size
<details>
  <summary>Evidence</summary>
  <br>
  
  Below is an example code snippet of how I modified the display grid styling adapt itself to different devices.
  
  ```CSS
  @media screen and (max-width: 960px) {
  main {
    display: grid;
    grid-template-columns: auto;
    justify-content: center;
  }
  ```
  
  |![image](https://user-images.githubusercontent.com/101563800/205528504-5635596f-c4bd-42e4-9f00-6b6456ef5689.png)|
  |:--:|
  |*Above: What the app looks like on a Samsung Galaxy S20 Ultra based on the media query*|
  </details>
  
