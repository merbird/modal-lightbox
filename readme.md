# Modal Lightbox - Slideshow Using jQuery
## Version History
1.0 - 3/9/2020 - Initial release
1.1 - 3/23/2020 - Add mobile swipe navigation and stop autoplay on next/prev button click or swipe 
1.2 - 11/24/2020 - Stop double slide skip by not allowing both touchstart and click events to fire

## Introduction
This is a modal image lightbox popup that displays a slideshow written in jQuery, CSS and HTML. 

![alt text](/markdown/slideshow.jpg "Example slideshow")
Key features include:
1. Supports multiple slideshows on the same webpage.
2. Responsive.
3. Option to display expand icon over original image to show it can be opened in lightbox.
4. Autoplay slideshow with user definable interval.
5. Multiple caption locations. 
## Prerequisites
 - This widget requires jQuery and 
 - Optional - Font Awesome (required if you want to use image expand icon).
## Setup
Download widget from GitHub ...

There are two files in the dist directory that need to be included in your html code. These files are bod-modal.js and modal.min.css. The css file should be included in the HEAD section of the webpage on which you want to display the modal lightbox.
```
<link rel="stylesheet" href="modal.min.css">
```
The js file should be included towards the bottom on your webpage before the closing <\body> tag.
```
<script src="bod-modal.js"></script>
```
If your webpage does not already include jQuery then this also can be added at the end of the webpage, but above the bod-modal.js file. For example, 
```
   <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
   <script src="bod-modal.js"></script>
</body>
```
## Incorporating Modal in Website
In order to use the modal image slideshow on a webpage you need to insert code that identifies a slideshow and sets display characteristics. For example, 
```
      <div class="bod-modal" data-interval="4" data-title="right">
         <div class='bod-expand-icon'>
            <a href="full-image-link.jpg" title="Caption Text to display on slide"><img src="image-to-display-on-webpage.jpg" alt="Alt title"></a>
         </div>
         <div class='bod-expand-icon'>
            <a href="full-image-link.jpg" title="Caption Title"><img src="webpage-image.jpg" alt="Alt title"></a>
         </div>
      </div>
```
### Slideshow Container
The slideshow container is identified by the bod-modal class. Each instance of the bod-modal class identifies a different slideshow.  
#### Autoplay
data-interval identifies the autoplay duration in seconds. If this is set to "0" then the slideshow will not autoplay, "2" would wait 2 seconds between slide etc.
#### Caption Location 
data-title identifies the slide caption location. If this is not specified / missing then no caption will be displayed. 
- "left" - displays in bottom left.
- "right" - displays in bottom right.
- "center" - displays in center.
### Image Container
Each image that is to be displayed in the lightroom slideshow should take the format: 
```
   <div class='bod-expand-icon'>
      <a href="full-image-link.jpg" title="Caption Text to display on slide"><img src="image-to-display-on-webpage.jpg" alt="Alt title"></a>
   </div>
```
#### Expand Icon
The optional bod-expand-icon class triggers the display of the expand icon in the top right corner of the image.

![alt text](/markdown/expand.jpg "Expand Icon")

This icon uses Font Awesome, a copy of which can be found in the dist/fonts directory. If you want to display the expand icon then these fonts must be included in the head of your webpage, for example: 
```
<link rel="stylesheet" href="fonts/font-awesome.min.css">
```
#### Slideshow Image
The href points to the full size image you wish to display in lightbox/slideshow when the user clicks on the image referenced in the img tag. 

#### Title / Caption
The title attribute associated with the a tag defines the caption to be displayed over the slideshow image. 

If the title attribute is not defined, or if the if the data-title attribute (see Slideshow Container)  is not specified then no caption is displayed.  

