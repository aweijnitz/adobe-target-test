# Test Adobe Target
This repo contains a few minimal HTML files for some experimentation to understand the way Adoeb Target does image substitution.

## Test 0: dynamic-picture-element
Adds a ```picture``` element to the DOM dynamically, using javascript.

The initial DOM does not contain any images. Once the browser executes the
included javascript in the page, a ```picture``` element is added on the fly.

The added markup looks like this

     <picture>
         <source
             media="(min-width: 650px)"
             srcset="http://via.placeholder.com/650x150">
         <source
             media="(min-width: 465px)"
             srcset="http://via.placeholder.com/465x150">
         <img
             src="http://via.placeholder.com/350x150"
             alt="FALLBACK IMG VERSION">
     </picture>
     
     
## Test 1: lazy-sizes-picture-element
Includes a non-standard ```picture``` element, enhanced with the 
[Lazy Sizes](https://afarkas.github.io/lazysizes/index.html) library.

The markup looks like this

    <picture>
        <!--[if IE 9]><video style="display: none"><![endif]-->
        <source
                data-srcset="http://via.placeholder.com/500x150"
                media="(max-width: 500px)" />
        <source
                data-srcset="http://via.placeholder.com/1024x150"
                media="(max-width: 1024px)" />
        <source
                data-srcset="http://via.placeholder.com/1200x150" />
        <!--[if IE 9]></video><![endif]-->
        <img
                src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw=="
                data-src="http://via.placeholder.com/1024x256"
                class="lazyload"
                alt="FALLBACK IMAGE" />
    </picture>

