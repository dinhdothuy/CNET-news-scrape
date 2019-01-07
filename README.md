# News-Scrape https://cnetnewsscrape.herokuapp.com/
All the News from CNET That's Fit to Scrape
I created a web app that lets users view and leave comments on the latest news. But I did not actually write any articles; instead, I used Mongoose and Cheerio muscles to scrape news from CNET site.

App that accomplishes the following:

Whenever a user visits this site, the app should scrape stories from CNET.com and display them for the user. Each scraped article should be saved to application database. The app scrapes and displayes the following information for each article:

Headline - the title of the article

Summary - a short summary of the article

URL - the url to the original article

Users should also be able to leave comments on the articles displayed and revisit them later. The comments should be saved to the database as well and associated with their articles. Users should also be able to delete comments left on articles. All stored comments should be visible to every user.

________________
npm packages:

* express

* express-handlebars

* mongoose

* cheerio

* axios

In order to deploy this project to Heroku, we must set up an mLab provision. mLab is remote MongoDB database that Heroku supports natively. 
Follow these steps to get it running:

Create a Heroku app in project directory.

Run this command in Terminal/Bash window:

$ heroku login

$ heroku apps:create cnetnewsscrape

$ git push heroku master

$ heroku addons:create mongolab

This command will add the free mLab provision to the project.

connect mongo database to mongoose, do so the following way:
// If deployed, use the deployed database. Otherwise use the local news database
***
var MONGODB_URI = process.env.MONGODB_URI || "mongodb://localhost/news";

mongoose.connect(MONGODB_URI);
***

Helpful Links

https://docs.mongodb.com/manual/

https://mongoosejs.com/docs/

https://www.npmjs.com/package/cheerio

https://cheerio.js.org/

