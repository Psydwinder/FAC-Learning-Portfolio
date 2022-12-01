# Markup portfolio


## 1. Structure a site using semantic HTML to aid accessibility
<details>
  <summary>Evidence</summary>
  <br>
  Throughout our code we adhered as closely to the A11Y guidelines as we could to use the correct elements. This was so that a screen reader could read each element of our code and feed it back to the user.
  
  Below is an exmaple of our code where we have used semantics to make the code easier to read.
  
  In addition to this we have also add in a class to each element, so that a developer working on the code knows what each element pertains to.
  
  ```html
    <header>
      <nav class="navbar">
        <a href="#" class="nav-branding">NerdWhale</a>
        <ul class="nav-menu">
          <li class="nav-item">
            <a href="#home" class="nav-link">Home</a>
          </li>
          <li class="nav-item">
            <a href="#about" class="nav-link">About Us</a>
          </li>
          <li class="nav-item">
            <a href="#ourwork" class="nav-link">Our Work</a>
          </li>
          <li class="nav-item">
            <a href="#contactus" class="nav-link">Contact Us</a>
          </li>
        </ul>
      </nav>
  </header>
```
</details>

## 2. Make a web page more readable for screen readers

<details>
  <summary>Evidence</summary>
  <br>
  We have included alternative text on images to help screen readers understand and feed back to visually impaired users what the element pertains to.
  
  ```html
  <div class="home-img">
  <img src="img/Nerdwhale2-01.png" alt="company image" class="company-pic" />
  </div>
 ```
</details>

## 3. Design a UI without relying solely on colour, so that we don’t exclude colour-blind users

<details>
  <summary>Evidence</summary>
  <br>
  

  |![image](https://user-images.githubusercontent.com/101563800/203403742-7c70ef1d-0de8-4aa0-bcd4-dc92a02dafd4.png)|
  |:--:| 
  | *Above: The meet the team section of our agency website* |
  
  We approached this project with the intention of starting with as little colour as possible to cater towards colour blind users. However, as time went on we decided to also add in colours that could be easily read by individuals with conditions like dyslexia.
  
</details>

## 4. Ensure our UI has sufficient colour contrast so that everyone can perceive it comfortably

<details>
  <summary>Evidence</summary>
  
  
</details>

## 5. Use various tools to check that a website meets accessibility criteria

<details>
  <summary>Evidence</summary>
  
  We used a mixture of Chrome's Lighthouse Extension to check for any immediate faults in our website, for example images not having alt text. In addition to this we used W3's HTML Markup Validator to check for semantic errors within our code and minimise the number of errors we were seeing.
  
  |![image](https://user-images.githubusercontent.com/101563800/205083937-a656c717-1173-4b25-b081-83255584591c.png)|
  |:--:|
  | *Above: Using Chrome's Lighthouse Extension to measure the website aginst various metrics* |
  
  |![image](https://user-images.githubusercontent.com/101563800/205084952-9fd6072d-0f7b-4ff9-bc80-ae44a1631ab8.png)|
  |:--:|
  | *Above: Using W3's HTML Markup Validator* |

</details>

## 6. Ensure a website displays well on screens of different sizes

<details>
  <summary>Evidence</summary>
</details>

## 7. Use CSS media queries to ensure content is always presented effectively

<details>
  <summary>Evidence</summary>
</details>

## 8. Demonstrate a mobile-first approach to designing a website with a great user experience

<details>
  <summary>Evidence</summary>
</details>

## 9. Create an attractive and accessible colour palette for a project

<details>
  <summary>Evidence</summary>
</details>

## 10. Use CSS variables to apply repeated colours to HTML elements

<details>
  <summary>Evidence</summary>
</details>
