# Testing portfolio


## 1. Check that passing a given input into out tests returns the expected output
<details>
  <summary>Evidence</summary>
   
  One of the first tests I wrote was to test whether any text that is added into an input box can be added to the to do list. 
  
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

  // ADD tests
  test("Submitting a new task adds it to the list", () => {
    createTestTask("Task1");
    equal(testList.children.length, 1, "One task is added to the list");
    clearTest();
  });
  
  ```
  
  
  |![image](https://user-images.githubusercontent.com/101563800/205118479-544053f9-a6da-4f93-8f63-b02610e4c904.png)|
  |:--:|
  |*Above: What the test looks like in the console*|

</details>

## 2. Write tests to mimic the behaviour of a user performing different actions
<details>
  <summary>Evidence</summary>
</details>

## 3. Write testable, modular functions
<details>
  <summary>Evidence</summary>
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
  
