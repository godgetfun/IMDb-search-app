# IMDb-search-app

Warning: Please follow the steps in Sequence.
Folders must be placed in given directory only.


To setup Scrapy in your system consider this tutorial:

http://doc.scrapy.org/en/latest/intro/install.html

To configure scrapyd service consider this tutorial:

1. http://stackoverflow.com/questions/28852258/scrapy-script-called-via-shell-exec-doesnt-perform
2. http://stackoverflow.com/questions/22646323/windows-scrapyd-deploy-is-not-recognized

To setup curl in your system consider this tutorial:

http://stackoverflow.com/questions/21694051/scrapyd-where-do-i-get-to-see-the-output-of-my-crawler-once-i-schedule-it-using


The installation steps assume that you have the following things installed:

1. Scrapy 1.0 or above.
2. WAMP server (assuming you are using windows on your system).
3. Python 2.7
4. Configured Scrapyd service for deploying scrapy project. (open browser and type htpp://localhost:6800 to check).
5. Download curl for windows 7.(required for execute in php the scrapy command).

In this tutorial, I’ll assume that everthing above is already installed on your system.

1. Extract the google.rar to "C:/" drive.
2. google.rar contains the backend logic of the project based on Scrapy and python.
3. Open cmd and start scrapyd service: c:/users/xyz> scrapyd
4. Host the php site in wamp server by extracting the app.rar in /wamp/www/ 
5. run the "user.sql" in My-SQL of WAMP server to create database.
6. Default database name is "recommendationengine". Rest of things consult "user.sql".
7. By considering everthing default in WAMP, type htpp://localhost/app/index.php in Browser.
8. And follow the images in sequence available in "screens" folder to proceed.

About Frontend:

1. Theme used: tumblr theme with pure css.
2. php based.
3. On submitting actor/actress name in dashboard. It generates "input.txt" in "c:/google".
4. Then execute the scrapy API, which used the above generated "input.txt" to generate output in "c:/google/it.json".
5. The result is printed in table using the "it.json".

About Backend:

1. Scrapy + Python based.
2. On execution it recursively scrape pages from IMDb to get the data.
3. The actor/ actress name from frontend is converted into search string.
Ex. "Leonardo Dicaprio" is converted to "https://www.imdb.com/find?q=Leonardo+dicaprio+&s=nm" and rest process is done recursively on the basis of the result generated by the link.

