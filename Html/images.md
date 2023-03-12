# images

Images are like links, in the they require an attribute to work.

A link uses the href attribute to link to another file.
Images use the *src* attribute, which is short for source.

- < img src="image.jpg">

Images are different from other elements, in that they are self-closing.
-  img src="image.jpg">
- < img src="image.jpg" />
both are good.

## File path
Like links, we can point to external images by including the entire URL of the image, or we can point to images within our site by listing the file name.
- < img src="image.jpg">
- < img src="https://website.com/image.jpg">

## Alt text
Images are not valid without an alt attribute.
The alt attribute is used to describe the image.
- < img src="cute-cat.jpg" alt"a very cute cat">

If it is decorative element or logo, it doesn't need alt text(but it does still require the alt attribute.)
- < img src="logo.jpg" alt"">
- < img src="decorative-red-ball.jpg" alt"">

