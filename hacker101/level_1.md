# Level 1
Name:  _"Micro-CMS v1"_
## First Impression
This is a multi-flag challenge (4 flags).

Launching the challenge redirected me to a webpage with an unordered list of two links: "Testing" and "Markdown Test". After was a link that said "Create a new page". When clicking on the "Testing" link it redirected me to http://34.94.3.143/d40e147fc0/page/1:

[!["Testing page"](/images/L1-0.png)](http://34.94.3.143/d40e147fc0/page/1)

Clicking through the "Edit this page" led to http://34.94.3.143/d40e147fc0/page/edit/1:
[!["Edit Page for Testing page."](/images/L1-1.png)](http://34.94.3.143/d40e147fc0/page/edit/1)

If I clicked "Go Home" it would send me back to the initial page. I tried creating a new page and it was essentially the same as the Edit Page page but blank allowing you to input anything. Once I created a page with some random text I noticed that the URL to the page ended in /page/11 instead of /page/3. The reason I assumed it would be /page/3 was because both Testing and Markdown Test were /page/1 and /page/2 respectively. I created another page just to be sure and found this new page to be /page/12. This let me know that pages 3-10 were either already created or something else was going on.

## Solution 0
1. Manually entered the URL for http://34.94.3.143/d40e147fc0/page/3 to 10 looking for anything unusual. All returned 404 Not Found, except for /page/7 which returned 403 Forbidden. 

2. Since this was the only page that was Forbidden it seemed like there must be a flag hidden here. The question however is how to retrieve the contents of the page. Recall that the site allows us to edit pages and to get to the "Edit Page" page the URL has to end in /page/edit/x where x is a page number. Since we are trying to edit page 7, I entered http://34.94.3.143/d40e147fc0/page/edit/7 as the URL which led me to the flag in the content form. 

## Solution 1


## Solution 2
1. Since there are fields where I can send data that directly post as HTML, perhaps I can perform some injection by sending HTML tags instead of actual text. One such tag that is useful for testing this is the `<script>` tag which allows for JavaScript code to be run in HTML. In JS there is a function called alert(message) which opens up a popup with message. I tried this in the body section of page creation.

2. Unfortunately it seems that the body form sanitizes its input from scripts. However, notice that the title form does not. If we write the same code into the title form perhaps it will run.

3. While it doesnt run on the page itself, recall that the homepage lists all the pages titles, so our injection will also be listed there. Go back to the homepage and the flag will be in a popup.

## Solution 3

## Notes