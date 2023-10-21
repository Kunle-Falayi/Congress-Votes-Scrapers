# Congress votes scraper
There are two scrapers in this repo <br>
[The first one](https://github.com/Kunle-Falayi/congress_votes_scraper/blob/main/118thSession1stSessionVotes_Scraper.ipynb) scrapes all the votes per each congressmember. It gets the congressmembers' names, parties, vote cast, etc. 
[The second one](https://github.com/Kunle-Falayi/congress_votes_scraper/blob/main/108thCongressVoteLatestAction.ipynb) gets the title of each roll vote and the latest action which is found on the page the url embedded in the bill number leads to. For instance, open https://clerk.house.gov/Votes/2023100, then click the bill number, it opens another page with a different html structure. That page contains the progress of the bill. <br>
<hr> 
Unlike the first scraper where BeautifulSoup is used to get the actual votes for each roll call, the pages we are targetting for the latest actions load contents with JavaScript, which is why Selenium is used here. In the first few cells, Selenium dependecies are loaded and Chrome driver installed. <br>
<hr>
Before building the main scraper code, check the number of roll call votes for each session of the congress. In this case, it is the 108th Congress, which ran from 2003 and 2004. <br>
The 2003 session had 678 roll call votes. Luckily, the url for each roll call vote is structured thus: <br>
the base url  "https://clerk.house.gov/Votes" + "year" + "roll call number" = https://clerk.house.gov/Votes/20031 to https://clerk.house.gov/Votes/2003677<br>
<hr>
This makes it easy to iterate from the first roll call number to the last. And since the structure of the vote pages have not changed through the years, it is even easier to iterate throw multiple years and scrape all at the same time. But I advice scraping individual session/year to make it easier to catch errors.<br>
Once the two scrapers complete its work, join both data.
