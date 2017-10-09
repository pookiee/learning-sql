# learning-sql
This will be a place to hold my sql progress

Beginning to learn SQL. I have completed the khan academy, and code academy sql classes which I thought were sufficient to teach the basics. I then moved onto https://github.com/tthibo/SQL-Tutorial which taught basically the same stuff but without pseudo code and it was on an actually sql database program SQLITE which I will be using since I don't wanna buy mySQL or microsoft sql server.
SQLITE is pretty good at basically everything basic except large datasets and client interactions. And for my data sets I've chosen small datasets because when I imported a larger set of about 10,000 entries it crashed my computer. So I will use data sets that won't crash my computer https://perso.telecom-paristech.fr/eagan/class/igr204/datasets

Today I was working on the dataset of cereal and I noticed that there is a correlation between the rating of the cereal and ingredients like sugars, carbs, and fats. The highest rating cereals have lower sugars, fats, and carbs.

SELECT fat, sugars, sodium, rating FROM cereal WHERE rating > 60 ORDER BY name
![sql cereal 1](https://user-images.githubusercontent.com/31829494/31058412-f1a1d744-a6a7-11e7-9559-dca65aeaf330.PNG)
An SQL query walks sees two tables he walks up and asks "can I join you?"


Today I learned how to combine unique SQL queries into one query using the UNION term which combines SELECT statements that could usually not be combined such as what I did looking up the average of sugars under a different where value (shelf). It is incredibly helpful because it allows efficiency when working. And It appears that 
![sql cereal 2](https://user-images.githubusercontent.com/31829494/31257226-4536d1e2-a9ec-11e7-8412-595e9b63c386.PNG)


I also figured out how to use mulitplayer functions when selecting a column. I used both the average and round function in the query to find the augmented potassium from the cereal table. The round function in SQLite is unique because you first enter the value that you want to round then the value you want it rounded to; it will automatically round off decimals unless otherwise noted in the second value of the round. ![sql cereal 3](https://user-images.githubusercontent.com/31829494/31257801-9ef7f6ea-a9ef-11e7-877c-962b3ac0998f.PNG)


SQl Injection notes from https://www.veracode.com/security/sql-injection  
SQL injections result from insufficient protection a website’s database security, people who use these tricks can get data from a website such as: passwords, email address, credit card, and much more. SQL injections happen when a person enters in SQL queries to a website, such as adding improper syntaxes to the asked information. If a website asked for your username and password a person could enter in kris’  for the username, if the website didn’t take precautions to prevent injections. When the person enters this in (kris’) with the apostrophe into the website with low protection the website could reveal the name of tables and information allowing the “hacker” to make SQL queries that relate to the databases meaning the database could reveal private information. This works because all websites (or most) when they ask for a password and/or username they compare the answer you gave with a data set inside of the database, if it matches (or is true) then you are allowed in. 

SQL allows for people to do the following:
~Logging into a website without correct information. 
~Altering data by either adding or deleting data values into the database. For example you could change someone's bank balance (but it's unlikely because banks won’t fall for SQL injections).
~The final thing that SQL injections allow is the ability to receive data that is private to people. For example getting credit card information.

SQL injections are two part attacks
First the user will enter in random data that the website would not expect to be entered in, this includes names with weird syntaxes, queries, and other bigs a phrase. People try to test out the website seeing how it responds.
The second part is entering in actual queries to get data back or get accesses to the website.


