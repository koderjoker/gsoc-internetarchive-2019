# Google Summer of Code 2019 at the Internet Archive


## Improving site navigation for archive.org


<p align="center"><img src="https://user-images.githubusercontent.com/30471843/63679971-35411380-c810-11e9-954e-7a5c937ca7a8.png"></p>


### Introduction

The Internet Archive is a non-profit library committed to Universal Access to Knowledge. In its 23 years of operation, the Internet Archive and its community have archived millions of web pages, books, texts, audio tracks, videos, images, and software (and thus, have rescued them from being lost to history). These items are made freely available to the public to consume and repurpose through the Internet Archive’s flagship website, Archive.org.

Because of the Internet Archive, millions of patrons from all over the globe now have a chance to access media which their local libraries and archives have never held or made access to them before. However, having the right content is not good enough. It is imperative that users are able to easily navigate through this content to find and view what they are searching for, regardless of the device used or disabilities that they may have to contend with.

Thus, my goal for this Google Summer of Code was to “Improve site navigation for archive.org” through researching, prototyping and developing relevant components and features at <a href="https://github.com/internetarchive/iaux">IAUX</a>, the Internet Archive’s monorepo for Archive.org UX development and prototyping.


### Stack used
Technologies that I worked with during my Google Summer of Code
- HTML
- CSS
- JavaScript
- React
- LitElement
- Storybook
- Sketch
- Jest
- React Test Renderer
- Enzyme
- React Testing Library
- Git
- Github


### Before Google Summer of Code
I have always been in love with books, ever since my childhood. However, it was very difficult to find titles I wanted to read since there has been, and still is, a severe dearth of good libraries in India.

Come my later years in high school when I fell in love with coding and college where I fell in love with development and open source culture. I soon started to search for an open source project that interested me, and where I could volunteer.

Thus I chose to begin my experience with volunteering at an open source organisation by contributing to Openlibrary, the world's largest non-profit, open source, digital public library, by merging a pull request for a linting issue as part of Hacktoberfest in October. I became a regular contributor January onwards, and started attending Openlibrary's community calls. I helped out by redesigning and implementing our book list pages, book edition component, search pages and raising and resolving issues for navigation and accessibility. 

Soon I branched out by helping in component development and documentation at IAUX, and applied for Google Summer of Code in the same.


## Google Summer of Code


### Flattening the directory structure and cleaning up the repo
I kickstarted my Google Summer of Code journey by focusing on flattening our directory structure, ensuring that all examples ran in storybook, closing resolved issues and helping out by reviewing and merging in pull requests pending pre gsoc to pave way for our upcoming tasks. To implement the same, I became familiar with storybook and studied our pre existing components and their working. 

Along with the above, a new component for the tracklist by a volunteer was successfully reviewed and merged in. I researched on the possibility of creating a separate component for our svgs as proposed by another volunteer, made an attempt for the same and discussed the pros and cons for the same in our user experience forum.

Master issue

Sub issues

Relevant pull requests


### Redesigning the search result card system
The archive’s uneven search tile system has been one of its greatest obstacles to accessibility and navigation, and thus was one of my sub goals to tackle. 

For the same I did an in depth study on the current situation of our tiles and listed all its issues that would be needed to be resolved. I studied Sketch and the use of its various plugins and followed up to coordinate with our UI and UX engineer Jim and built a strategy together to tackle the tile designs and improve my workflow in Sketch. 

We decided to first work towards equalising all cards heights, then followed by replacing our information messages with badges and solving colour contrast issues in our colour palette. I presented the latest version of the prototypes in our biweekly user experience forum and kept adding on small tasks, reiterated on and redesigned the tiles multiple times based on continuous review and feedback for until the final prototypes were confirmed and approved.

Final prototypes for height standarisation and redesigning the information overlay can be found <a href="https://github.com/internetarchive/iaux/issues/195#issue-456375923">here</a> and <a href="https://github.com/internetarchive/iaux/issues/196#issuecomment-514803299">here</a>!

Master issue

Sub issues


### Building the Internet Archive's music player
Building the youtube channel for our music player in React was the biggest task I undertook, and I spent most of my Google Summer of Code period on its development, enhancement, testing and bug fixing; getting it ready for its ship to production.

My main task was to build the youtube wrapper component and integrate it in the bigger music player component. I met up with Isa to break down our task and decide what aspects to prioritise. Our first aim for the youtube wrapper was to integrate the YouTube iframe api and replace the default embedded, synchronise with our tracklist component, handle youtube player errors gracefully and to autoplay the video and shift track accordingly. I was also given full reign to make changes in multiple existing parent and child components of the music player to accommodate the same. 

I picked out parts from the youtube iframe's api that would help in our endeavour and noted down legal/technical difficulties that the building youtube player would face and rediscussed them with Isa. I made notes and sketched out the flow of data, relevant components, files and variables to keep track of all necessary changes. I reduced lines of codes/complexity by writing the most elegant solution possible and replaced legacy lifecycle methods.

Once a stable version of the component was created I discussed existing issues on error handling, state management, integration hiccups with main music component and possible refinements for the music player with Isa. Isa also gave me access to her BrowserStack account for testing purposes. Thus we went through numerous cycles of testing and bug fixing in order to make it meet user experience expectations. I made a tasklist to tick off in the main pull request to keep track.

We discussed the state of the music player at different points of time with Jim, and he created a document to list Music Player specs to meet before our player could move to production. Discussion for the music player occurred in multiple one-on-one calls, updates on the same were given in stand up calls and feedback was asked for in our user experience forum.

The music player finally shipped to production on August 10 🎉

<a href="https://www-isa.archive.org/details/cd_backstreet-boys_backstreet-boys/">NOTE: You can see the music player at work at archive.org!</a>

Issues

Pull requests


### Researching React testing libraries/utilities for component testing
When the youtube player reached its first stable state I started to write tests in Jest for the same. However, it soon became apparent that the currently used testing library (react-test-renderer) wasn’t optimal for our use, and thus I spent some time studying the pros and cons of using `react-test-renderer`, `enzyme` and `react-testing-library`. 

This was a rather unique study as there were no straightforward and clearcut comparisons online and the endeavour required me to deep dive into the documentation, explore the libraries’ chats and github comments and issues in repositories that chose to use any of the libraries and understanding and combining the views of developers on the same. In the end I determined that using react-testing-library would be the best for our purposes.

Summarised points and references can be found <a href="https://github.com/internetarchive/iaux/issues/226">here</a>. I plan to elaborate on the same through an article in the near future.


### Building the mobile topnav

Working and enhancing the topnav was something I was interested in from the start, due to the huge potential in improving it and resolving its multiple existing accessibility and navigational traps.

After a call with Isa we agreed that I was to build the new mobile topnav using LitElement, and we consulted Jason who had prior experience in building the archive’s radio player with the same. Afterwards I had a meeting with Jim who introduced me to the workings of the prototype of the mobile topnav, and I broke my work down into smaller issues to tackle one by one. I set up my environment and studied css animations and LitElement in preperation. I also surveyed and research implementations on other websites and studied best accesaccessibility practices for developing website navigational features.

After a couple of issues faced due to pre existing issues with the navbar I had a brief discussion with Isa, and it was decided to 
- Build the navbar from scratch with minimal code and discard the previous code. Later on built a new desktop nav, thus extending the mobile topnav’s utility
- Rewrite the styles from scratch due to the large amount of unused css and the unexpected styles caused due to it
- Removing Bootstrap as a dependency for new components in IAUX due to it’s unwanted effects on self written styles and pre-existing accessibility issues

I soon had the navbar done and the pull requests are being reviewed and merged one by one!
Master issue
Sub issues:
Pull requests:
