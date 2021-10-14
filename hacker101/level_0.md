# Level 0
Name:  _"A little something to get you started"_
## First Impression
Launching the challenge redirected me to a webpage with a line of text that said:
> "Welcome to level 0. Enjoy your stay." 

and nothing else.

## Solution
1. Opened the source with Inspect in Mozilla Firefox. This gave HTML code for the site with a head element and body element. As expected the body element had the text mentioned above. However the head element included a style element containing `background-image: url("background.png");` which I found interesting.

2. Since this style element is telling me that the background.png is some data being requested as the background image, I figured that there must be some kind of GET request involved. By navigating to the Network tab of the developer tools it becomes clear that my assumption was right.

3. Open up the response from the GET request for background.png and theres an HTML file with the flag in it.

## Notes
- Originally I tried this in Google Chrome and could not find anything. Weirdly enough Chrome showed that there was no response from the GET request. On previous web related challenges Chrome has also given me issues so from now on I will use Mozilla as default.