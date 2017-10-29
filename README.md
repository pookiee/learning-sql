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
The second part also called attack is where the dangerous part of the injection happens because this is where people are able to get information from the website which causes havoc. And almost anyone can do SQL injections with knowledge of SQL since there are automatic programs that will allow people to do “hack” without knowledge. SQL injections should be a thing of the past because the way the injections happen are so simple and it requires minimum security measures to protect against injections. There are four ways that SQL injections be prevented: the first way that injections can prevented is,  by testing the website routinely; the second way that injections can prevented is, by specify the parameters of the information meaning you can avoid getting unexpected answers to the query. By specifying what you will want to receive you you should be able to stop people from scouting out your website by putting syntaxes in it or doing some other spooky things. Also to prevent this you could make sure you have separate tables so that data that can be stolen be data that would be ok, like the heights of people. It wouldn't matter if that was stolen. Also adding accesses/security keys to the data when is being asked for and retrieved. So that a normal person would not have the security key to get important datasets from a website. A majority of websites with admin powers such as chat room websites lack proper security so it is very easy for “hackers” to get accesses to admin position and destroy the websites. This can be done by logging in through their username but entering a true statement with proper syntax into the website (needs java or php). Because the website lacks proper security measures the person could get in just by entering in true statements like  1=0 or 1=1 the website will grant access to the user because when there are syntaxes it will interpret it as a statement not a query, and the php or java will usually log users in when the query comes back as true, this skips the entire querying part of sql injections and is rarely used. 

https://www.hackthissite.org/playlevel/2  won’t be able to see it if you aren’t logged in

So although this isn't completely sql related but a lot of it is using HTML/Java I have been using the website hts (hack this website) to practice my skills on sql injection and one of the realistic mission problems I had to do was gain admin power to a white supremacist website. I will explain how I did it. So first off you always have to read the entire website before you do anything to see for anything spooky stuff. After reading the website I saw that there was no place to enter in a password or username to get login to the website, but the people who posted did have usernames meaning the login must have been hidden, so I open up the source code for it, after scrolling for a while through the code I notice an out of place link that leads into a login page. I click on the link and see that it doesn’t look secure at all so I test out the normal ‘ for the username but when it fails and doesn’t lead me to anything useful I try something a little more advanced, I hit them with a ‘or 1=1--. Which is probably a medium security level SQL injection technique, this then completes the level. 

3801b4af0150

realistic mission #4 was a real world application of SQL injection. When I first saw the website I looked it over and visted all the sub-domains of it. Looking at the DNS of the website it was obvsious that it uses MySql because of the PHP after this I began looking for the table name which was email, I figured this out after entering a 'or 1=1-- then I entered in my email and found that the entire name, email. After I figured out the table columns I entered in a UNION ALL SELECT and filled out null for the values like products the other column names then put * for the email list into the link up above and it brought me to see the emails of the buyers.

