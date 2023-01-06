

![Ready day 1](https://github.com/knitterJ/advent-of-css-2021-2022/blob/master/2.eCommerceComp/explanation-progress-track/day-1-setting-up-the-background-based-on-3-svgs/images/ready-day-1.png)

h1. Setting the background

The background of the project is set up with 3 images/blobs

h2. How to provide links to the images?

There are basically two ways of providing the links to the images.

h3. First (straightforward way that I chose) is via HTML


<blockquote>
Absolute positioning allow you to define exact location of an element on a page, regardless of others (the element becomes independent from others). Use absolute positioning to set the exact location of for example a background image on a page, even if the content and other elements of the page change.
</blockquote>



h3. Second way is via CSS property background: url()
<code>
.bg__top-right{
background: url("images/bg__left.svg")
}
</code>

Some folks treat it as better practice, but the approach brought me a lot of hassle.
Providing url of the svg image in CSS as the background, makes it disappear and from the very beginning you start with a lot of confusion.

In this case, apart from providing position of the image (like in the first shown way) it's necesary to define:

<ul>
  <li>background-repeat: no-repeat</li>
  <li>background-size: contain</li>
</ul>


<blockquote>
<code>Background-size: contain</code> should be used to scale the background image and to make sure the entire image is visible. It prevents the image from being distorted or overstreched.
</blockquote>

Here's the working code for someone who'd like to define svg image this way
<code>
.bg__top-right{
  background-repeat: no-repeat
  background-position: center left
  background-size: contain
  position: absolute
  left: 0
  top: 40vh
  height: 40vh
  width: 20vw
</code>
