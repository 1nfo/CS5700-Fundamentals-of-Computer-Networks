HIGH LEVEL APPROACH

1. The project aims to implement a webcrawler, which can collect/scourge data from a social networking site - [Fakebook](http://cs5700sp17.ccs.neu.edu) including the collection of 5 secret flags which are hidden in the HTML headers.
2. Through GET and POST messages in HTTP, we are establishing login session using username and password, csrftoken and collecting the IDs to create successive sessions using those IDs.
3. These IDs are then sent to the server and the program deals with the status code from the server, through which other links are opened to scourge for more flags.
4. To facilitate crawling in all the links, we are establishing a loop, through which all the links are visited and flags are gathered, the program exits after collecting 5 flags.
5. Beautiful Soup module is used to parse links from the server.

CHALLENGES FACED

1. Debugging - We faced difficulty in debugging the correct syntax for GET and POST messages.
2. Implementing infinite loop - While dealing with the status codes from the server, it was difficult to implement a list differentiating between the visited and non-visited links.
3. Making the program time effective, initially the program took a lot of time to converge and give the flags, later with some modifications in the loop and lists, we could obtain the flags within 5 minutes.

TEST CASE

Positive Testing

./webcrawler 001682189 GSKM5WNY
./webcrawler 001216417 J3HESUNA

Negative Testing

./webcrawler J3HESUNA 001216417
./webcrawler GSKM5WNY 001682189
./webcrawler ABCDEFGH 001234567
./webcrawler GSKM5W 001682189
./webcrawler GSKM5WNY 00168218
./webcrawler GSKM5WNY 001216417 001682189
./webcrawler GSKM5WNY J3HESUNA 001682189


