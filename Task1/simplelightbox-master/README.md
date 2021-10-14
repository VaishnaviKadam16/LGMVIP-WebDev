# simplelightbox
Touch-friendly image lightbox for mobile and desktop

### Features
* responsive
* touchfriendly
* swipe gestures for next/previous image
* easy to install, easy to use
* minimalistic
* Only some css is included. You can change the style like you want!
* lots of options
* preloading next and previous image
* Android, iOs and Windows phone support
* CSS3 Transitions with fallback for older browsers
* Works in every modern Browser, even in IE 9+
* Can use jQuery 1.x,2.x and 3.x, but don't need
* Keyboard support
* Pinch to zoom
* Double-tap to zoom

### Install
```sh
// YARN
yarn add simplelightbox

//Bower
bower install simplelightbox

//NPM
npm install simplelightbox
```

After that include simple-lightbox(.min).css and simple-lightbox(.min).js to your page.

### Usage
When using the standalone variant (`simple-lightbox(.min).js`)
```javascript
new SimpleLightbox('.some-element a', { /* options */ });
```

The jquery-compatible (`simple-lightbox.jquery(.min).js`) variant works as before (v1.x):
```javascript
$('.some-element a').simpleLightbox({ /* options */ });
```

### Markup
For the default setup, you just need links that are pointing to images.
```markup
<div class="gallery">
    <a href="images/image1.jpg"><img src="images/thumbs/thumb1.jpg" alt="" title=""/></a>
    <a href="images/image2.jpg"><img src="images/thumbs/thumb2.jpg" alt="" title="Beautiful Image"/></a>
</div>
```
The markup inside the A-Tags can be whatever you want. In this example thumbnails of the big images. The Title Tag is by default used to show a caption.
For a whole example just look at the demo folder.

### Events
| Name | Description |
| ---- | ----------- |
| show.simplelightbox | this event fires before the lightbox opens |
| shown.simplelightbox | this event fires after the lightbox was opened |
| close.simplelightbox | this event fires before the lightbox closes |
| closed.simplelightbox | this event fires after the lightbox was closed |
| change.simplelightbox | this event fires before image changes |
| changed.simplelightbox | this event fires after image was changed |
| next.simplelightbox | this event fires before next image arrives |
| nextDone.simplelightbox | this event fires after next image was arrived |
| prev.simplelightbox | this event fires before previous image arrives |
| prevDone.simplelightbox | this event fires after previous image was arrived |
| nextImageLoaded.simplelightbox | this event fires after next image was loaded (if preload activated) |
| prevImageLoaded.simplelightbox | this event fires after previous image was loaded (if preload activated) |
| error.simplelightbox | this event fires on image load error |

**Example**  
```javascript
$('.gallery a').on('open.simplelightbox', function () {
  // do something…
});

$('.gallery a').on('error.simplelightbox', function (e) {
  console.log(e); // some usefull information
});
```

### Public Methods
| Name | Description |
| ---- | ----------- |
| open | Opens the lightbox with an given Element |
| close | Closes current openend Lightbox |
| next | Go to next image |
| prev | Go to previous image |
| destroy | Destroys the instance of  the lightbox |
| refresh | Destroys and reinitilized the lightbox, needed for eg. Ajax Calls, or after dom manipulations |

**Example**  
```javascript
var gallery = $('.gallery a').simpleLightbox();

gallery.next(); // Next Image
```

### Multiple Lightboxes on one page
You can have multiple lightboxes on one page, if you give them different selectors. Here is a small example:
```javascript
var lightbox1 = $('.lighbox-1 a').simpleLightbox();
var lightbox2 = $('.lighbox-2 a').simpleLightbox();
```

### Customization

You can customize Simplelightbox by changing the style in simplelightbox.css.

If you are using SASS, you can customize Simplelightbox with the following variables

### Contributing
**using gulp**  
Run `gulp watch` to enable continous watching of both src/simple-lightbox.js and src/simple-lightbox.scss. Both files will be compiled to dist/simple-lightbox.js and dist/simple-lightbox.css respectively. Open dist/index.html in your browser to inspect your changes...

**Building**  
Just call `gulp build` to have all files and variants created inside dist!
