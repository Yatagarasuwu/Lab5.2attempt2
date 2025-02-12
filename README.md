# web-dev-starter

This is a starter project for web development with no frameworks and minimal
dependencies. It is intended to be a starting point for web development projects
that are written in plain HTML, CSS, and JavaScript.

## Getting Started

To get started, clone this repository and run the following commands:

```bash
npm install
```
This will install the necessary dependencies for the project.

## Development

It is recommended to use the VSCode Live Server extension to run the project
locally. This will allow you to see changes in real-time as you make them. There
is no need to run a build process or refresh the page manually. Additionally,
you do not need to setup a local server to run the project.

## Testing

There are no relevant tests for this file.


## Access project website
Assuming you have the VSCode Live Server Extension, simply press ctrl+shift+P and then type "Live preview: Start server" and you will see the website.

## Accessibility Lab Answers

## Color

The text is difficult to read because of the current color scheme. Can you do a test of the current color contrast (text/background), report the results of the test, and then fix it by changing the assigned colors?

Yes. I am not using test.js for this, as the readings have provided https://webaim.org/resources/contrastchecker/.  
The website states that our green hexcode (#008000) as a background, with black text (#000000), gives 4.08:1 which is unacceptable for normal text. 

Therefore, I changed the background to a normal white, which gives us a 21:1 contrast ratio. This also looks similar to


### Semantic HTML
The content is still not very accessible — report on what happens when you try to navigate it using a keyboard.
First and foremost, utilizing the TAB key is quite annoying in this website. All it really does is navigate us through the "related" links, and then the sound section area. The user can't even access the comments button. 
The arrow keys, page up, page down and more are useful, but there should be a smoother implementation of the website to make the comments button available and each section TAB-able.

Can you update the article text to make it easier for screen reader users to navigate?

Yes. Firstly, I added tabindex for the major headings in the website. I understand that in our readings, we were advised to be careful with tabindex, 
as retroactively changing the website in this manner is more trouble than simply using the correct semantics in the first place.
However, in this case, I feel like it is relevant to a good web experience.

The arguably more important change is that the comments section button is now actually a button, rather than a div. This makes it accessable to keyboard only users.

The navigation menu part of the site (wrapped in <div class="nav"></div>) could be made more accessible by putting it in a proper HTML semantic element. Which one should it be updated to? Make the update.
Note: You'll need to update the CSS rule selectors that style the tags to their proper equivalents for the semantic headings. Once you add paragraph elements, you'll notice the styling looks better.

### The Images
The images are currently inaccessible to screen reader users. Can you fix this?

Yes. The two images now have alt-text and a title for their photos. 

### The Audio Player
The <audio> player isn't accessible to hearing impaired (deaf) people — can you add some kind of accessible alternative for these users?

This part was difficult to understand. I tried to use the WebVTT as the readings showed, but they dont really apply to audio non-video to my knowledge. I ended up settling for just a small transcript below it.
This is likely wrong, so I'm looking forward to the code-reviews to figure out what I was supposed to do.

The <audio> player isn't accessible to those using older browsers that don't support HTML audio. How can you allow them to still access the audio?

Taken from the reading, https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Accessibility/Multimedia , I gave the users the link to the audio instead if their HTML doesn't support the audio.

### The Forms
The <input> element in the search form at the top could do with a label, but we don't want to add a visible text label that would potentially spoil the design and isn't really needed by sighted users. How can you add a label that is only accessible to screen readers?

The WAI-ARIA Reading helps here. It tells me to use aria-label so I did. 

The two <input> elements in the comment form have visible text labels, but they are not unambiguously associated with their labels — how do you achieve this? Note that you'll need to update some of the CSS rule as well.

I used "label for", as it lets me specify, unambiguously, the ID that the section/label is focusing on. They work in tandem with the current labels.

Note that you'll need to update some of the CSS rule as well.

I feel like it looks better in the new formatting? Its  more centered and larger.

## The Show/Hide Comment Control
The show/hide comment control button is not currently keyboard-accessible. Can you make it keyboard-accessible, both in terms of focusing it using the tab key and activating it using the return key?

Whoops, I did this earlier in the Semantic HTML section. I made it a button instead of a div.

### The Table
The data table is not currently very accessible — it is hard for screen reader users to associate data rows and columns together, and the table also has no kind of summary to make it clear what it shows. Can you add some features to your HTML to fix this problem?

I added the summary section inside the <table> with <table summary="">. 
I added a caption.
In our readings theres a section on table formatting, but it was actually already setup! No tbody,thead etc needed.
I did atleast add scope so the reader can decipher if it is a row or col.
## Other Considerations?
Can you list two more ideas for improvements that would make the website more accessible?

First and foremost, the "Welcome to our wildlife website" (the font 7) text has a bad contrast -- I decided to make it brown, which might look a bit worse, but it has much better contrast onto the off-white background:  5.27, compared to 1.34. 5.27 still isnt perfect, but it works for large text, and represents bears while letting the text-shadow still visible (unlike black).

Secondly, I would recommend using WAI-ARIA landmarks potentially. I didn't implement this, but If I were too, I would most likely place them for the man section, the nav section, the footer, and the related section.
