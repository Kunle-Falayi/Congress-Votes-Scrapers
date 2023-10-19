# Congress votes scraper
The data targeted by this scraper is the U.S. Congress voting data [here](https://clerk.house.gov/Votes) <br>
Since this scraper uses Selenium, the first couple of cells are simply importing the dependencies and installing the Chrome driver. <br>
Before building the main scraper code, I check the number of roll call votes for each session of the congress I am taretting. In this case, it is the 108th Congress, which ran from 2003 and 2004. <br>
The 2003 session had 678 roll cal votes. Luckily, the url for each roll call vote is structured according thus: <br>
the base url  "https://clerk.house.gov/Votes" + "year" + "roll call number" = https://clerk.house.gov/Votes/20031 to https://clerk.house.gov/Votes/2003677<br>
This makes it easy to iterate from the first roll call number to the last. And since the structure of the vote pages have not changed through the years, it is even easier to iterate throw multiple years and scrape all at the same time. But I advice scraping individual session/year to make it easier to catch errors.<br>

