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
  </details>

## 5. Apply event listeners to HTML form elements
<details>
  <summary>Evidence</summary>
  </details>
  
## 6. Use scope to control what variables are accessible inside functions and blocks
<details>
  <summary>Evidence</summary>
  </details>
  
## 7. Use CSS grid to create complex layouts
<details>
  <summary>Evidence</summary>
  </details>

## 8. Use CSS grid to make layouts that adapt to the viewport size
<details>
  <summary>Evidence</summary>
  </details>
  
