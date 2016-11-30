# How to run website
[Here's the website hosted on Github](https://fradgile.github.io/frontend-nanodegree-mobile-portfolio/) or you can do the following

1. Clone or download repository.
2. Open index.html in your favorite browser.


# PageScore improvements
#### index.html modifications

\# | What was changed? | How? | Purpose |
 ------------ | :----------- | -----------: |-----------:
1 | pizzeria.jpg | Compressed and resized using imageoptimizer.net| Reduce download size.
2 | Google Fonts | Removed as it did not seem to be used anywhere | Reduce download size.
3 | perfmatters.js | Minified to `perfmatters.min.js` | Reduce download size.
4 | perfmatters.min.js | Added `async`  to scrippt tag | Prevent blocking
5 | perfmatters.min.js | Moved to the bottom of body| Prevent blocking
6 | Google Analytics | Moved to the bottom of body | Prevent blocking
7 | print.css | Minified to `print.min.css`| Reduce download size.
8 | style.css | Minified to `style.min.css`| Reduce download size.
9 | style.min.css | Inlined | Prevent blocking.


### PageScore Testing
1. [Installed the npm http-server package to serve my pages locally.](https://www.npmjs.com/package/http-server)
2. [Installed ngrok to expose my local website to the internet.](https://ngrok.com/)
3. [Analyzed my website using PageSpeed Insight Tool.](https://developers.google.com/speed/pagespeed/insights/)

### Score Before Modifications
![ScreenShot](/Screenshots/PageSpeedBefore.png)
### Score After Modifications
![ScreenShot](/Screenshots/PageSpeedAfter.png)

# Getting Rid of Jank - Frame Rate & Computational Efficiency
#### main.js modifications

\# | Modification | Purpose
----------- | ------------ | :----------- |
1|Replaced querySelector with getElementById | More performant
2|Replaced querySelectorAll with getElementsByClassName | More performant
3| Moved code out of loops where possible. In particular see `changePizzaSizes()`, `updatePositions()` and `document.addEventListener('DOMContentLoaded', function()` | Unnecessary repition of code
4|Reduced the number of sliding pizzas from 200. See `document.addEventListener('DOMContentLoaded', function()` | No need for 200. Just slowing everything down.

### Frame Rate Before Modifications
![ScreenShot](/Screenshots/Part2Before.png)
### Frame Rate After Modifications
![ScreenShot](/Screenshots/Part2After.png)


***
***

## Website Performance Optimization portfolio project

Your challenge, if you wish to accept it (and we sure hope you will), is to optimize this online portfolio for speed! In particular, optimize the critical rendering path and make this page render as quickly as possible by applying the techniques you've picked up in the [Critical Rendering Path course](https://www.udacity.com/course/ud884).

To get started, check out the repository and inspect the code.

### Getting started

####Part 1: Optimize PageSpeed Insights score for index.html

Some useful tips to help you get started:

1. Check out the repository
1. To inspect the site on your phone, you can run a local server

  ```bash
  $> cd /path/to/your-project-folder
  $> python -m SimpleHTTPServer 8080
  ```

1. Open a browser and visit localhost:8080
1. Download and install [ngrok](https://ngrok.com/) to the top-level of your project directory to make your local server accessible remotely.

  ``` bash
  $> cd /path/to/your-project-folder
  $> ./ngrok http 8080
  ```

1. Copy the public URL ngrok gives you and try running it through PageSpeed Insights! Optional: [More on integrating ngrok, Grunt and PageSpeed.](http://www.jamescryer.com/2014/06/12/grunt-pagespeed-and-ngrok-locally-testing/)
