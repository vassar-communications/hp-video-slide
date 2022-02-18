# Homepage video slide

## How it works

This setup involves two videos: a looping teaser, displayed in the hero slideshow where an image would typically be, and the full video, displayed in a Bootstrap modal window. Both videos autoplay; the teaser plays on page load, and the full video plays when the modal is opened. The full video pauses (but does not rewind) when the user closes the modal.

Two components are required.


### Hero slideshow

`hero-slideshow.txt` contains the autoplaying video loop (what appears in the slide area) and the CSS for both the custom video slide and the modal. This goes into the caption field of a "hero slideshow component" slide.

### Modal block

`video-modal-and-script.txt` contains the modal window markup. This should be placed in a regular Main Content component. That's because the modal markup can't be inside a slideshow caption; something about the slideshow causes the modal backdrop to appear on top of the modal window, so the modal window needs to be outside the slideshow. It can still be invoked from the slideshow, though.

### The CSS

Unfortunately, there's currently no way to target a specific carousel slide. The best I can do is target a Drupal-generated ID of the carousel item's contents. It looks like `media-id--XXXXX`.

**Note:** If you change the video slide image, that ID will change, so the custom styling will no longer apply. You'll need to update the ID in `style.scss` and recompile the CSS.