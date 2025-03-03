# Assignment-1-Solving-WikiRacer-Step-by-Step
Assignment 1: Solving WikiRacer Step by Step


Download  Link :https://programming.engineering/product/assignment1-wikiracer-solution-guide/

Description
5/5 – (2 votes)
One interesting place to fnd interesting patterns is Wikipedia. For example, we can play a game called WikiRacer, where we try to move from one article to another with the fewest number of clicks. Try a round online before you move on!

For your frst assignment, you will build a standard C++ program that plays WikiRacer! Specifcally, it will fnd a path between two given Wikipedia articles in the fewest number of links. We’ll refer to this path as a “ladder.”

To simplify this assignment, we removed the user-facing part of Wikiracer. A simple version of the front-end is available as totally optional extra practice. In this assignment, you will implement the core of this interesting search algorithm that fnds the ladder.

We already implemented what you might call the front end of our WikiRacer game. The front end is the user-facing side of the game: the code necessary to take in a flename with WikiRacer inquiries and print out the resulting WikiLadders is implemented. The function called by the front end, findWikiLadders is backend of this program: the user doesn’t need to know how it works or call it directly, they just want results! This assignment, you are stepping behind the curtain and implementing parts of findWikiLadder in main.cpp and the function findWikiLinks in wikiscraper.cpp

A broad pseudocode of the algorithm that findWikiLadders will use to fnd a ladder from startPage to endPage is as follows:

To find a ladder from startPage to endPage:

Make startPage the currentPage being processed.

Get set of links on currentPage.

If endPage is one of the links on currentPage:

We are done! Return path of links followed to get here.

Otherwise:

Visit each link on currentPage in an intelligent way and search each of those pages in a similar manner.

To simplify the implementation and allow for some testing, we will do this in two parts (A and B). For part A, you will be implementing parts of findWikiLinks in wikiscraper.cpp. This function will deal only with the part of our algorithm that gets the set of links on currentPage. In Part B, you will be implementing parts of findWikiLadder which will use the findWikiLinks function as described in the pseudocode.

IfDownloadyouhaven’talready,pleaseAndfollowSettheinstructionsUpAssignmentonthispagebeforeproceeding. Please do both the one-time instructions and the instructions for editing each assignment. If you have any questions at all, please don’t hesitate to send us an email!

ForPartpart A,Ayou will be implementing parts of findWikiLinks in wikiscraper.cpp. To test your changes with a custom autograder that will run only for code in wikiscraper.cpp, run ./test-wikiscraper.sh (instead of ./build_and_run.sh). This function will deal only with the part of our algorithm that gets the set of links on currentPage:

To find a ladder from startPage to endPage:

Make startPage the currentPage being processed.

Get set of links on currentPage.

If endPage is one of the links on currentPage:

…

Part A of the assignment will be to implement a function

unordered_set<string> findWikiLinks(const string& page_html);

that takes a page’s HTML in the form of a string as a parameter, and returns an unordered_set<string> containing all the valid Wikipedia links in the page_html string. For our purposes, a link must satisfy the following:

It must be of the following form:

<a href=”/wiki/PAGE_NAME”>LINK TEXT</a>

PAGE_NAME does not contain the characters # or :

Aside: did you know that if you click the frst link on any Wikipedia page repeatedly, you’ll eventually always end up at Philosophy 97% of the time?

For those who don’t remember, an unordered_set behaves exactly like a set but is faster when checking for membership (in the Stanford library it is called a HashSet).

Webpages are written in a language known as HTML.

All you need to know about HTML is how links are formatted:

