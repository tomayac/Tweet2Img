# Tweet2Img
Convert a public Tweet into an image &amp; alt text

Uses Selenium's Webdriver to launch a Firefox or Chrome instance and takes a screenshot. Uses the Twitter embed API to get a copy of the text and any alt text. An HTML representation is copied to the clipboard.

Usage:

* `python tweet2img.py 123` will get the Tweet with ID 123, save a WebP screenshot, and print out the alt text.
* `python tweet2img.py 123 --thread` as above, but will include the parent Tweet if this is a reply.
* Screenshot and alt text are saved in the `output` directory.
* Clipboard receives a copy of the HTML - including data-encoded image - ready to paste in.
    * `<a href="https://twitter.com/edent/status/123"><img src="data:image/webp;base64,Ukl..." width="550" height="439" alt="Screenshot from Twitter. 2022-08-19T13:36:44.000Z. Description."/></a>`

Known bugs:

* Fractional Scaling may produce slightly fuzzy images (Wayland related?)
* Alt text contains t.co URls rather than the expanded ones (could use entities?)
* Many other thing (probably?)