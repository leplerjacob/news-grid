# News Grid Website

<!-- Steps will be marked with Step # comment blocks -->

<!-- ******************************  Step 1  ************************************ -->

<!-- Sub steps will be marked with following notation #.# etc.-->

<!-------------------- 1.2 ---------------------->

<!-- Chapters within each Sub step will be marked following notation #.#.# -->

<!-- ########## 1.2.3 ##########-->

****************************************************************************************************************************

<!-- ******************************  Step 1  ************************************ -->
## Step 1

<pre>
First you want to create all the folders and files that you can

Gather images and icons that you'll need

Also gather links to resources if possible (e.g. fontawesome or bootstrap)
</pre>

<!-------------------- 1.1 ---------------------->
### HTML boilerplate

```HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <!-- Added -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.13.0/css/all.min.css" integrity="sha256-h20CPZ0QyXlBuAw7A+KluUYx/3pK+c7lYEpqLTlxjYQ=" crossorigin="anonymous" />
    <link rel="stylesheet" href="style.css">
    <link rel="stylesheet" media="screen and (max-width: 768px)" href="mobile.css">
    <link rel="shortcut icon" type="image/x-icon" href="/favicon.ico">
    <title>NewGrid | Latest News</title>
    <!-- ^^^ -->
</head>
<body>

</body>
</html>
```
<pre>
Recall that a favicon is the symbol that appears within the tab on a browser of a website
</pre>

<img src="./screen_captures/Step 1/favicon_exhibit_1.JPG" alt="">

<!-- ******************************  Step 2  ************************************ -->
## Step 2

<!-------------------- 1.1 ---------------------->
### HTML Initial Body Markup | index.html

<pre>
Lets start with a navigation bar using nav tag

Usually we'd use flex for navigation bar, but in this case we'll use the grid system.

Also, we'll add icons and links to popular social media sites within the navbar

This time, well go...
nav > #main-nav > .container > items
</pre>

```HTML
<body>
    <!-- Added -->
    
    <nav>
        <div id="main-nav">
            <div class="container">
                <img src="../img/logo.png" alt="" class="logo">
                <div class="social">
                    <!-- Input icons for facebook, twitter, instagram, and youtube -->
                    <a href="http://facebook.com"><i class="fab fa-facebook fa-2x" target="_blank"></i></a>
                    <a href="http://twitter.com"><i class="fab fa-twitter fa-2x" target="_blank"></i></a>
                    <a href="http://instagram.com"><i class="fab fa-instagram fa-2x" target="_blank"></i></a>
                    <a href="http://youtube.com"><i class="fab fa-youtube fa-2x" target="_blank"></i></a>
                </div>
                <ul>
                    <li><a href="index.html" class="current">Home</a></li>
                    <li><a href="about.html">About</a></li>
                </ul>
            </div>
        </div>
    </nav>
    
    <!-- ^^^ -->
</body>
```
<pre>
What we have so far...
</pre>
<img src="../Notes\screen_captures\Step 2\exhibit_2_update_1.JPG" alt="">

<!-- ******************************  Step 3  ************************************ -->
## Step 3

<!-------------------- 3.1 ---------------------->
### CSS/HTML Initial Base Styling Plus Navigation| Style.css | 3.1

<!-- ########## 3.1.1 ##########-->
#### CSS Variables | Style.css | 3.1.1

<pre>
When planning your website, establish primary color combinations that will be used throughout the website, like in boxes, buttons, links, paragraphs, headers, etc.
</pre>
```CSS
:root {
    /* Think of colors that will be the background for boxes behind text, as well as text color */
    --primary-color: #c72727;
    --secondary-color: #f99500;
    --light-color: #f3f3f3;
    --dark-color: #333;
    --max-width: 1100px;
}

.category {
    /* In this website, there are categories of topics like sports, entertainment, etc. Each of these categories will have buttons that have different colors */
    --sports-color: #f99500;
    --ent-color: #a66bbe;
    --tech-color: #009cff;
}
```
<!-- ########## 3.1.2 ##########-->
#### HTML Fonts | index.html | 3.1.2

<pre>
Grab the font "Lato", and "Staatliches" from google fonts
</pre>

```HTML
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.13.0/css/all.min.css" integrity="sha256-h20CPZ0QyXlBuAw7A+KluUYx/3pK+c7lYEpqLTlxjYQ=" crossorigin="anonymous" />
    <!-- Added -->
    <link href="https://fonts.googleapis.com/css?family=Lato|Staatliches&display=swap" rel="stylesheet">
    <!-- ^^^ -->
    <link rel="stylesheet" href="style.css">
```
<!-- ########## 3.1.3 ##########-->
#### CSS Resets | style.css | 3.1.3

<pre>
Now we'll style a few resets in CSS.

Things we are making initial settings for are *, body, a, ul, img, and h# tags.
</pre>

```CSS
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Lato', sans-serif;
    line-height: 1.5;
    background: var(--light-color);
}

/* Any of these stylings are going to be considered 'base' styling */
a {
    color: #333;
    text-decoration: none;
}

ul {
    list-style: none;
}

/* This will set the image to span the entire box element it is contained within */
img {
    width: 100%;
}

h1,h2,h3,h4,h5,h6 {
    font-family: 'Staatliches', cursive;
    margin-bottom: .55rem;
    line-height: 1.3;
}
```
<!-- ########## 3.1.4 ##########-->
#### CSS Utilities | style.css | 3.1.4

<pre>
Containers will keep elements within a specified width, as well as not show overflowing items
</pre>

```CSS
/* Because we will be using a container within the nav... */
.container {
    max-width: var(--max-width);
    margin: auto;
    padding: 0 2rem;
    /* Set overflow so it always shows the content within and will not overflow the container */
    overflow: hidden;
}
```
<!-- ########## 3.1.5 ##########-->
#### CSS Navigation | style.css | 3.1.5

```CSS
    #main-nav {
        background: #fff;
        /* Because a navigation bar will be placed at top of the screen, we will set the position:sticky. That way, it will be placed at the top of the viewport screen as we scroll down */
        position: sticky;
        top: 0;
        /* We set this so then the nav will always precede other elements, even if there are overlays (because we'll set other elements to be under) */
        z-index: 2
    }
```
<pre>
If you take a look at the navbar, there is a container div as a direct child of the nav tag. Becuase of this, if you set grid to the #main-nav, then it will only make one grid item of the .container class element, not the elements within the .container class, which, is what we want.
</pre>

```CSS
/* Make the logo, social items, and the ul all grid items */
#main-nav .container {
    display: grid;
    grid-template-columns: 6fr 3fr 2fr;
    padding: 1rem;
    align-items: center;
}
```
<pre>
This is how the navbar looks after applying the grid.

Also take note that 6fr 3fr 2fr leaves the img twice the size of the social links, and the ul links two-thirds the size of the social links
</pre>

<img src="../Notes\screen_captures\Step 3\exhibit_3_navbar_grid_initial.JPG" alt="">

<pre>
Logo is a bit big, lets resize...
</pre>
```CSS
#main-nav .logo {
    width: 180px;
}
```
<!-- ########## 3.1.6 ##########-->
#### CSS Additional #main-nav Styling | style.css | 3.1.6

<pre>
Keep in mind that when you want to align individual items, target the item in css and use 'justify-self' as opposed to 'justify-content'
</pre>

```CSS
#main-nav ul {
    /* In order to push the ul links all the way over to the right */
    justify-self: end;
    /* We will display:flex the items of the ul */
    display: flex;
}

#main-nav ul li a {
    padding: 0.75rem;
    font-weight: bold;
}

#main-nav ul li a.current{
    background: var(--primary-color);
    color: #fff;
}

#main-nav ul li a:hover {
    background: var(--light-color);
    color: #333;
}

#main-nav .social{
    /* Center the social items to the middle of its grid */
    justify-self: center;
}

/* I am going to add additional hover features to each of the social links... */
#main-nav .social .fa-facebook:hover{
    background: #fff; 
    color: #3b5998;
} 
#main-nav .social .fa-twitter:hover{
    background: #fff; 
    color: #1da1f2;
} 
#main-nav .social .fa-instagram:hover{
    background: #fff; 
    color: var(--dark-color);
} 
#main-nav .social .fa-youtube:hover{
    background: #fff; 
    color: #ff0000;
} 

#main-nav .social i {
    color: #777;
    margin-right: .5rem;
}
```

<!-- ******************************  Step 4  ************************************ -->
## Step 4

<!-------------------- 4.1 ---------------------->
### CSS/HTML Overlay & Showcase | index.html, style.css | 4.1

<!-- ########## 4.1.1 ##########-->
#### CSS Add A Header .Showcase | index.html | 4.1.1
<pre>
We will now move on over to the showcase...

We will use a header tag with the #showcase, and a container to container the actual grid container.

The grid container will be .showcase-container, which, will only contain one grid item. Now the grid item will have both a .category and .category-sports in order to display category features, but category-sports centered colors.
</pre>

```HTML
    </nav>

    <!-- Added -->
    <header id="showcase">
        <div class="container">
            <div class="showcase-container">
                <div class="showcase-content">
                    <div class="category category-sports">Sports</div>
                    <h1>Some Sports Article</h1>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Eum tenetur quae reiciendis voluptas cupiditate deleniti nostrum illum delectus, quam, animi, minus id aliquid optio veniam. Itaque saepe tempora similique eveniet.</p>
                    <a href="article.html">Read More</a>
                </div>
            </div>
        </div>
    </header>
    <!-- ^^^^^ -->
    
</body>
```
<pre>
    We'll now add the css...
</pre>

<!-- ########## 4.1.2 ##########-->
#### CSS For the Header .Showcase | style.css | 4.1.2

```CSS
#showcase {
    color: #fff;
    /* We will add an overlay of an image on the showcase */
    background: #333;
    padding: 2rem;
    position: relative;
}

#showcase:before {
    content: '';
    /* Here we are adding an image to span the entire #showcase. The image will have an opacity that will expose the background that is black */
    background: url('../img/featured.jpg') no-repeat center center/cover;
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    opacity: 0.4;
}

#showcase .showcase-container {
    display: grid;
    /* We will create two columns. However, because there is only one item, the grid will still create space for the other empty half */
    grid-template-columns: repeat(2, 1fr);
    /* Justify-content will center the text to the middle horizontally */
    justify-content: center;
    /* Align-items will center the text to the middle vertically */
    align-items: center;
    height: 50vh;
}
```
<pre>
Get the showcase text to show more definitively by changing the z-index of the text only. A z-index:1 will bring it to the forefront above other elements, which, are by default 0 or underfined
</pre>

```CSS
#showcase .showcase-content {
    z-index: 1;
}
```

#### CSS Add CSS To A Utility Class .Category & .Category-sports | style.css | 4.1.3

<pre>
We will now add utility class css to a .category & .category-sports class...
</pre>

```CSS
.category {
    display: inline-block;
    color: #fff;
    /* Make the font smaller */
    font-size: 0.55rem;
    /* Make text uppercase */
    text-transform: uppercase;
    padding: 0.4rem 0.6rem;
    border-radius: 15px;
    margin-bottom: 0.5rem;
}

.category-sports { background: var(--sports-color) }
.category-ent { background: var(--ent-color) }
.category-tech { background: var(--tech-color) }
```

<pre>
This is what we have so far...
</pre>

<img src="../Notes\screen_captures\Step 4\exhibit_4_category_showcase.JPG" alt="">

#### CSS Add CSS TO Utility Class .Btn | style.css | 4.1.4

<pre>
For core button.
</pre>

```CSS
.btn {
    display: inline-block;
    /* Take away the border in the case we apply class to actualy button */
    border: none;
    /* Default color will use variable for dark black color */
    background: var(--dark-color);
    color: #fff;
    padding: 0.5rem 1.5rem;
}
```
<pre>
We'll also move the button of the showcase category away from the content paragraph, as well as other btn classes and styling...
</pre>

```CSS
.btn-light {
    background: var(--light-color);
}
.btn-primary {
    background: var(--primary-color);
}
.btn-secondary {
    background: var(--secondary-color);
}

/* Button that has width that goes all the way across */
.btn-block {
    display: block;
    width: 100%;
    text-align: center;
}

.btn:hover {
    opacity: 0.9;
}
```


<!-- ******************************  Step 5  ************************************ -->
## Step 5

<pre>
These steps will be to create an article grid layout for the website
</pre>

<!-------------------- 5.1 ---------------------->
### HTML/CSS Articles Grid | 5.1

<pre>
In this section we the flow of html will follow...

section > h2 h2 > .articles-container > article.card and so on

We will create a class "card", similar to that of bootstrap. In this case we are kind of creating our own "framework"
</pre>

<!-- ########## 5.1.1 ##########-->
#### HTML Articles HTML | index.html | 5.1.1

<pre>
Lets add some HTML...
</pre>

<!-- *************************************************start of html****************************************************************** -->
```HTML
    <!-- Added -->
    <section id="home-articles" class="py-2">
      <div class="container">
        <div class="articles-container">
          <!-- Card 1 -->
          <article class="card">
            <img src="../img/articles/ent1.jpg" alt="" />
            <div>
                <div class="category category-ent">Entertainment</div>
              <h3>
                  <a href="article.html"
                  >Lorem ipsum dolor sit amet consectetur.</a
                  >
                </h3>
                <p>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem
                    fugit dolore rerum molestiae nulla assumenda deserunt! Incidunt
                    nostrum sequi dolorem.
                </p>
            </div>
        </article>
        
        <!-- Card 2 -->
        <article class="card">
            <div class="category category-sports">Sports</div>
            <h3>
                <a href="article.html">Lorem ipsum dolor sit amet consectetur.</a>
            </h3>
            <p>
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem
                fugit dolore rerum molestiae nulla assumenda deserunt! Incidunt
                nostrum sequi dolorem.
            </p>
        </article>
        
        <!-- Card 3 -->
        <article class="card">
            <img src="../img/articles/tech1.jpg" alt="" />
                <div class="category category-tech">Technology</div>
                <h3>
                  <a href="article.html">Lorem ipsum dolor sit amet consectetur.</a>
                </h3>
                <p>
                  Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem
                  fugit dolore rerum molestiae nulla assumenda deserunt! Incidunt
                  nostrum sequi dolorem.
                </p>
            </article>
            <!-- Card 4 -->

        <article class="card">
            <div class="category category-sports">Sports</div>
            <h3>
                <a href="article.html">Lorem ipsum dolor sit amet consectetur.</a>
            </h3>
            <p>
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem
                fugit dolore rerum molestiae nulla assumenda deserunt! Incidunt
                nostrum sequi dolorem.
            </p>
            <img src="../img/articles/sports1.jpg" alt="" />
              </article>

              <!-- Card 5 -->
              <article class="card">
                <img src="../img/articles/tech2.jpg" alt="" />
                    <div class="category category-tech">Technology</div>
                    <h3>
                      <a href="article.html">Lorem ipsum dolor sit amet consectetur.</a>
                    </h3>
                    <p>
                      Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem
                      fugit dolore rerum molestiae nulla assumenda deserunt! Incidunt
                      nostrum sequi dolorem.
                    </p>
                </article>

                <!-- Card 6 -->

                <article class="card">
                    <div class="category category-sports">Sports</div>
                    <h3>
                        <a href="article.html">Lorem ipsum dolor sit amet consectetur.</a>
                    </h3>
                    <p>
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem
                        fugit dolore rerum molestiae nulla assumenda deserunt! Incidunt
                        nostrum sequi dolorem.
                    </p>
                </article>

                <!-- Card 7 -->
                <article class="card">
                    <div>
                        <div class="category category-ent">Entertainment</div>
                        <h3>
                            <a href="article.html"
                            >Lorem ipsum dolor sit amet consectetur.</a
                            >
                        </h3>
                        <p>
                            Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem
                            fugit dolore rerum molestiae nulla assumenda deserunt! Incidunt
                            nostrum sequi dolorem.
                        </p>
                    </div>
                    <img src="../img/articles/ent2.jpg" alt="" />
                </article>

        </div>
      </div>
    </section>

    <!-- ^^^^^ -->
```
<!-- *************************************************end of html****************************************************************** -->


<!-- ########## 5.1.2 ##########-->
#### CSS Card Utilities Class | style.css | 5.1.2


<pre>
We have created a few classes like .home-articles, .articles-container, and .card classes. Lets now add some CSS for those...

Okay...so not much CSS here. This will create a "card"-like container for all the articles in the grid
</pre>

```CSS
.card {
    background: #fff;
    padding: 1rem;
}  
```

<!-- ########## 5.1.3 ##########-->
#### CSS .Home-Articles Class CSS | style.css | 5.1.3

<pre>
Now we will input CSS for .Home-articles class
</pre>

```CSS
/* This makes a grid with 3 columns and equal sizes */
#home-articles .articles-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1rem;
}

/* This targets any element that is a first child of .articles-container */
#home-articles .articles-container > *:first-child, 
#home-articles .articles-container > *:last-child {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
    /* This will make the first-child element to span across two item slots on the grid */
    grid-column: 1 / span 2;
    /* This centers both the image and the grid within that element-grid-item to the middle vertically */
    align-items: center;
}

#home-articles .articles-container > *:last-child {
    grid-column: 2 / span 2;
}
```


<pre>
This is what we have so far...
</pre>

<img src="../Notes\screen_captures\Step 5\exhibit_5_articles_grid.JPG" alt="">

### CSS/HTML Add Background & Padding Classes | style.css | 5.2

#### CSS Background Classes & Padding | style.css | 5.2.1

<pre>
We'll now add some background and padding classes
</pre>

```CSS
/* Background Colors */
.bg-dark {
    background: var(--dark-color);
    color: #fff;
}

.bg-primary {
    background: var(--primary-color);
    color: #fff;
}
.bg-secondary {
    background: var(--secondary-color);
    color: #fff;
}

/* Padding Y-axis */
.py-1 {
    padding: 1.5rem 0;
}
.py-2 {
    padding: 2rem 0;
}
.py-3 {
    padding: 3rem 0;
}

/* Padding all around */
.p-1 {
    padding: 1.5rem;
}
.p-2 {
    padding: 2rem;
}
.p-3 {
    padding: 3rem;
}
```

#### HTML Add Classes to Elements | index.html | 5.2.2

<pre>
As we change the backgrounds to come of the grid elements there was a problem...
</pre>
```HTML
        </article>
        
        <!-- Card 2 -->
        <!-- Changes -->
        <article class="card bg-dark">
                        <!-- ^^^^^ -->
            <div class="category category-sports">Sports</div>
```
<img src="../Notes\screen_captures\Step 5\exhibit_6_issue_with_htag.JPG" alt="">

<pre>
As you can see the second grid item (one with black background), the h tag element has not changed color even though we specified color:#fff on the CSS class. 

In order for the color to change, we must target the element specifically
</pre>

```CSS
/* Here we are targeting any text tags that have a parent element, or itself having a bg-dark,bg-primary, or bg-secondary tag to have a white color text */
.bg-dark h1,
.bg-dark h2,
.bg-dark h3,
.bg-dark a,
.bg-primary h1,
.bg-primary h2,
.bg-primary h3,
.bg-primary a,
.bg-secondary h1,
.bg-secondary h2,
.bg-secondary h3,
.bg-secondary a {
    color: #fff;
}
```
<img src="../Notes\screen_captures\Step 5\exhibit_7_issue_cleared.JPG" alt="">

<pre>
Now that that is cleared, we will add a background class to more html elements...
</pre>

```HTML
    </article>

    <!-- Card 6 -->
                    <!-- Changed -->
    <article class="card bg-primary">
                        <!-- ^^^^^ -->
        <div class="category category-sports">Sports</div>
        <h3>
```

<!-- ******************************  Step 6  ************************************ -->
## Step 6

<pre>
</pre>

<!-------------------- 6.1 ---------------------->
### Footer With Grid | 6.1

<!-- ########## 6.1.1 ##########-->
#### HTML Footer Elements | index.html | 6.1.1



<pre>
Were going to have a grid of 4 columns per row, and the second row will span the enter column grid
</pre>

```HTML
      </div>
    </section>

    <!-- Added -->
    <!-- Footer -->
    <footer id="main-footer py-2">
        <div class="container footer-container">
            <div>
                <img src="../img/logo_light.png" alt="">
                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eaque impedit quis labore libero vitae id voluptas eum veritatis recusandae deleniti!</p>
            </div>
            <div>
                <h3>Email Newsletter</h3>
                <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit.</p>
                <form>
                    <input type="email" placeholder="Enter Email">
                    <input type="submit" value="Subscribe" class="btn btn-primary">
                </form>
            </div>
            <div>
                <h3>Site Links</h3>
                <!-- We'll make a utility class -->
                <ul class="list">
                    <li><a href="#">Help & Support</a></li>
                    <li><a href="#">Privacy Policy</a></li>
                    <li><a href="#">About Us</a></li>
                    <li><a href="#">Contact</a></li>
                </ul>
            </div>
            <div>
                <h2>Join Our Club</h2>
                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Numquam, rem.</p>
                <a href="#" class="btn btn-secondary">Join Now</a>
            </div>
            <div>
                <p>Copyright &copy; 2019, All Rights Reserved</p>
            </div>
        </div>

    </footer>

    <!-- ^^^^^ -->
  </body>
```
<!-- ########## 6.1.2 ##########-->
#### CSS Footer Styling | syle.css | 6.1.2

<pre>
We'll now add some footer CSS...
</pre>

```CSS

```

```CSS

























```CSS
<img src="" alt="">
<img src="" alt="">
<img src="" alt="">
<img src="" alt="">

<pre>
</pre>
<pre>
</pre>
<pre>
</pre>
<pre>
</pre>
<pre>
</pre>
<pre>
</pre>
<pre>
</pre>
<pre>
</pre>
<pre>
</pre>