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
  
  Below are a few examples of what the site looks like on two devices of varying sizes. 
  
  |![image](https://user-images.githubusercontent.com/101563800/205667761-dde0f43a-6aba-4685-99bc-a84e208a4723.png)|
  |:--:|
  |*Above: What the app looks like on a Samsung S8+*|

  |![image](https://user-images.githubusercontent.com/101563800/205668356-1ad9c967-a848-4fb2-958d-3279750755d4.png)|
  |:--:|
  |*Above: What the app looks like on an iPad Mini*|
  
</details>

## 7. Use CSS media queries to ensure content is always presented effectively

<details>
  <summary>Evidence</summary>
  
  Below is an example code snippet of a media query we used to ensure content is presented effectively on a device with a screen size less than 420px
  
  ```CSS
  @media (max-width: 420px) {
  body{
max-width: fit-content;
  }

  .navbar {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    background: var(--bg-color);
    z-index: 100;
    display: flex;
    align-items: center;
    justify-content: space-between;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    padding: 1rem;
  }

  .nav-menu {
    position: absolute;
    top: 75%;
    right: -100%;
    gap: 0;
    flex-direction: column;
    background-color: var(--bg-color);
    width: 40%;
    text-align: center;
    transition: 0.3s;
  }

  .nav-item {
    padding: 20px 0;
  }

  .nav-menu.active {
    right: 0;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  }

  .home-content {
    display: flex;
    flex-wrap: wrap;
    padding-left: 100px;
    padding-top: 20px;
    width: 100%;
  }
  
  .home-img {
    width: 1000px;
    height: 1000px;
    overflow: hidden;
    margin-bottom: 2rem;
  }
  
  .home-text {
    width: 400px;
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
    justify-content: center;
  }
 
  .home-text h1 {
    font-size: 2.5rem;
  }
  .home-text p {
    display: flex;
    flex-wrap: wrap;
    font-size: 1rem;
    margin-bottom: 1.5rem;
  }
  
  .section-heading {
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
    font-size: 3rem;
    text-transform: uppercase;
    color: var(--heading-color);
    text-align: center;
    margin-bottom: 2rem;
    font-weight: 100;
  }
  
  .project-container {
    display: grid;
    grid-template-columns: auto;
    justify-content: center;
    align-items: center;
    margin-left:30px;
  }

  .project-card .card-banner img {
    border-radius: 25px;
    transition: var(--transition-2);
    width: 300px;
    height: 429px;
    object-fit: cover; 
  }

  .description {
    max-width: 200px;
    width: 200px;
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
    font-size: small;
    position: absolute;
    margin: auto;
    margin-top: -225px;
    background-color: hsl(47, 100%, 69%);
    border-radius: 10px;
    padding: 50px;
    text-align: center;
    opacity: 0;
    transition: 0.5s ease;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  }
}

  ```
</details>

## 8. Demonstrate a mobile-first approach to designing a website with a great user experience

<details>
  <summary>Evidence</summary>
  
  Although we didn't design the website using a mobile-first approach, we did use media queries to allow the website to be read easily using a mobile.
  
  |![image](https://user-images.githubusercontent.com/101563800/205667761-dde0f43a-6aba-4685-99bc-a84e208a4723.png)|
  |:--:|
  |*Above: What the app looks like on a Samsung S8+*|
  
</details>

## 9. Create an attractive and accessible colour palette for a project

<details>
  <summary>Evidence</summary>
  
  For this project we decided to use a minimal colour palette so that there is a contrast between the text and the styling. 
  
  This is also the reason why we have intentionally spaced information out over the page. We utilised the white space so that the the user is not overloaded with information and is lead through the website absorbing as much information as possible.
  
  Keeping that in mind, we have sprinkled dashes of colour sporadically through the site, especially on the landing page as this is the first thing the user will see.
  
  |![image](https://user-images.githubusercontent.com/101563800/205671034-1baf17bc-31ff-4bc0-b053-aa3cfd3e5a36.png)|
  |:--:|
  |*Above: Colour that has been utilised on the landing page*| 

</details>

## 10. Use CSS variables to apply repeated colours to HTML elements

<details>
  <summary>Evidence</summary>
  
  Where possible we have defined root colours that could be utilised throughtout the stylesheet without having to enter the exact hexcode for that colour multiple times.
  
  ```CSS
  :root {
  --main-color: #647bff;
  --body-color: #090a1a;
  --container-color: #171b3c;
  --heading-color: #222231;
  --box-color: #0d0f26;
  --bg-color: #fff;
}
  ```
  ```CSS
  .navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background: var(--bg-color);
  ```
  *Above: The code snippet shows that I have use var(--bg-color) for the nav bar*
</details>
