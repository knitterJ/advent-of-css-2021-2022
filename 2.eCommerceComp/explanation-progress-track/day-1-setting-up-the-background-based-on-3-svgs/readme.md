
# 1. Setting up the background 

![Ready day 1](https://github.com/knitterJ/advent-of-css-2021-2022/blob/master/2.eCommerceComp/explanation-progress-track/day-1-setting-up-the-background-based-on-3-svgs/images/ready-day-1.png)

The background of the project is composed of 3 images/blobs, so first question in the project is:

## How to provide links to the images and how to position the 3 given images?

There are basically two ways of providing the links to the images.

### a) First straightforward and easy way - via HTML

`<img class="bg__left" src="images/bg__left.svg"/>`

Then in CSS, define the position of the image and make it independent from superior elements by `position: absolute;`

```
.bg__top-right{
    position: absolute;
    top: 10px; 
    right: 20px;
    
    /* not obligatory */
    max-height: 500px; 
    max-width: 600px;
    scale: 1.2;
}
```

>*Absolute positioning allow you to define exact location of an element on a page, regardless of other elements (the element becomes independent from >others). Use **absolute positioning** to set the exact location of for example of a background image on a page. **Even if the content and other elements >of the page change, it'll stay in the same absolute position**.*




### b) Second way - via CSS property background: url()
```
.bg__top-right {
background: url("images/bg__left.svg")
}
```

Some folks treat it as better practice, but the approach brought me a lot of hassle.
Providing url of the svg image in CSS as the background, makes it disappear and from the very beginning you start with a lot of confusion.

In this case, apart from providing position of the image (like in the first shown way) it's necesary to define:

<ul>
  <li>background-repeat: no-repeat;</li>
  <li>background-size: contain;</li>
</ul>

so you need to generate more lines of code and uderstand the topic well, in order to achieve the same effect as shown in the point [a)](<#a-first-straightforward-and-easy-way---via-html>)

>*`Background-size: contain` should be used to scale the background image and to make sure the entire image is visible. It prevents the image from being distorted or overstreched.*

Here's the working code for someone who'd like to define svg image this way:

```
.bg__top-right{
  /*All the properties provided below are obligatory*/
  background: url("images/bg__left.svg")
  background-repeat: no-repeat
  background-size: contain
  position: absolute
  left: 0
  top: 40vh
  height: 40vh
  width: 20vw
}
```
