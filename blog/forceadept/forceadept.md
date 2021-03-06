---
title: Web Scraping vs. Photographer Download Codes
subtitle:
tagline:
date: 2022-08-02
---

I went to a party with a very fancy photobooth last week. It would print out a film strip of the images immediately, and the photos were all uploaded to the photographer's website the next day. The only issue with all this is that the photos required a code to download them which the host of the party was never given. The host was content to just screenshot the images but that goes against my religion, so I had to find a better way.

The photographers website presented all the images as a gallery that required an email address to access (coincedentally with a full screen image of me and my friends behind). There was no actual registration or comfirmation involving the email address, so I am not sure why they do this. Once your pass the email form, you are presented with a gallery of all the images from the event, though only 16 load initially, with more appearing as you scroll. Upon hovering over a image, a download icon would appear, but clicking it would prompt you for the download code. Right clicking on the images did nothing, but given there were >250 images this wouldn't have been ideal even if it had worked.

The page source revealed that the images were being presented using standard `<img>` tags with direct links to the images. The direct image links were in the format `https://images.photographername.com/<eventnum>/<photouuid>-<size>.JPG`. After some trial and error the size went from `medium` all the way up to `xxlarge`. Perfect!

Should just be a matter of scraping all the `src` attributes from all the `img` tags right?

##
