# mp3

Movie SQLs
Guest Lecturer
Alex Keller, Professor of Film and Media Studies, Director of Film and Media Studies Program
Learning Goal
To write database queries in SQL
Readings
Ch. 12 of Modern Data Science with R
Netflix’s Secret Special Algorithm Is a Human, The New Yorker
Netflix’s dumbed-down algorithms, Reuters
How Netflix Reverse Engineered Hollywood, The Atlantic
Quantitative analysis of the evolution of novelty in cinema through crowdsourced keywords, Nature
Likability-Based Genres: Analysis and Evaluation of the Netflix Dataset
How racially skewed are the Oscars?, The Economist
Mini-Project
You will investigate a Film and Media Studies question of interest. Your deliverable will be a 5-minute class presentation (to your peers) and a blog post written in R Markdown.

In groups of three, please choose a topic from the following list illuminated by Prof. Keller:

Westerns over time: The Western is a central U.S. genre, not just to Hollywood and mainstream film (think Stagecoach, 1939 and The Searchers, 1956), but also to independent film production (Brokeback Mountain, 2005). Film critics have pronounced the Western dead repeatedly, and, so far, always wrongly. Between 1900 and 2015, when and how has Western film production peaked and ebbed? What might account for this, and does the IMDB define a Western in the 1950 in the same way as it does in 2000?

See info_type_id = 3 AND info = 'Western'
Genre Multiplicity: Prof. Keller explained how the labor model in Hollywood has changed over time, specifically with respect to the 1947 court decision that broke up the vertical integration of studios. Is it true that movies made today tend to have overlapping genres in a way that they did not in the past? Is is true that older movies tended to fit squarely in one genre, while more recent movies tend to span multiple genres? Is there a historical moment where this genre complexity begins? Does it have patterns of any discernible kind?

See info_type_id = 3
Sequels with SQL: Hollywood seems to be more repetitive than it used to be. Is this true? We now have not only sequels, but also remakes and reboots. Are these follow-up films more common today than they used to be? Can you trace the evolution of sequels across time in Hollywood? Are sequels more frequent today? Is the spacing between a sequel and its original shorter than it used to be?

Community Detection and Missingness: In statistics, data are often missing. Yet the difference between data that are missing at random versus missing systematically is crucial. What movies are present in the IMDB? We know there are box office Hollywood movies, independent films, experimental/avant-garde films, adult films, and foreign films. What films are missing? How does a film merit inclusion in the imdb.com data base? Can you think of any films that are not in the database? Are there entire areas of moving image production that imdb.com simply doesn’t recognize (e.g. youtube.com)? If so, what accounts for that? Could you create a visualization showing the source of every film in the IMDB? What communities are present? What communities are not present? When you “map” these data, look beyond geography.

Your project will use data stored in the IMDB to address one of the four topics outlined above. You will write several queries in SQL that will pull in data relevant to your question. Examination of that data will inform your response to the question, and you will then formulate your arguments accordingly. Recall that (as always) communication is a critical component of data science, so details like axis labels, figure captions, spelling, and grammar, are just as important as writing your queries correctly and making a logical argument.

Be extra careful when writing your queries! Just because the query executes without an error does not mean that it will return exactly what you want. The computer is dumb—it just carries out instructions. You are smart—it’s your job to translate your ideas into a syntax that the computer can understand. Know your data!!!

Data
Data are available through the imdb database located on scidb.smith.edu. Please see me for login instructions, or use the special functions built into the mdsr pacakge.

library(mdsr)
library(RMySQL)
db <- dbConnect_scidb(dbname = "imdb")
db %>%
  dbGetQuery("SELECT * FROM kind_type;")
##   id           kind
## 1  1          movie
## 2  2      tv series
## 3  3       tv movie
## 4  4    video movie
## 5  5 tv mini series
## 6  6     video game
## 7  7        episode
Rubric
There are 14 points available on this Mini-Project.

Baseline
+1 for having an .Rmd that compiles without errors
+1 for including a problem statement (what are you trying to figure out?)
+1 for using data from more than one table in your analysis
+1 for readable, well-documented code (i.e. appropriate comments, using line breaks, breaking code up into logical chunks, following a style guide)
+1 unnecessary messages from R are hidden from being displayed in the HTML
Average
+1 for joining multiple tables using SQL
+1 for using precise SQL queries (i.e. requesting only the columns you need, rather than requesting everything and filtering in R)
+1 for using efficient SQL queries (i.e. making use of an index column to speed things up, and including a comment indicating this)
+1 for using a data graphic to articulate your findings
+1 for including relevant external information to your analysis (e.g. important cultural context that the reader might not have, historical events that could be related to what you found, etc.)
Advanced
+1 for using a GitHub repository and including a link to it at the bottom of your submission
+1 for including a (well-supported!) alternate hypothesis / explanation for what you found
+0–2 WOW factor: awarded at the professors’ discretion for submissions that are exceptionally compelling
Created by Ben Baumer and R. Jordan Crouser.
