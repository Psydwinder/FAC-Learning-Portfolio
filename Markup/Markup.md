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

## 4. Ensure our UI has sufficient colour contrast so that everyone can perceive it comfortably

## 5. Use various tools to check that a website meets accessibility criteria

## 6. Ensure a website displays well on screens of different sizes

## 7. Use CSS media queries to ensure content is always presented effectively

## 8. Demonstrate a mobile-first approach to designing a website with a great user experience

## 9. Create an attractive and accessible colour palette for a project

## 10. Use CSS variables to apply repeated colours to HTML elements
