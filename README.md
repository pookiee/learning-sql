# learning-sql
This will be a place to hold my sql progress

Beginning to learn SQL. I have completed the khan academy, and code academy sql classes which I thought were sufficient to teach the basics. I then moved onto https://github.com/tthibo/SQL-Tutorial which taught basically the same stuff but without pseudo code and it was on an actually sql database program SQLITE which I will be using since I don't wanna buy mySQL or microsoft sql server.
SQLITE is pretty good at basically everything basic except large datasets and client interactions. And for my data sets I've chosen small datasets because when I imported a larger set of about 10,000 entries it crashed my computer. So I will use data sets that won't crash my computer https://perso.telecom-paristech.fr/eagan/class/igr204/datasets

today I was working on the dataset of cereal and I noticed that there is a correlation between the rating of the cereal and ingredients like sugars, carbs, and fats. The highest rating cereals have lower sugars, fats, and carbs.

SELECT fat, sugars, sodium, rating FROM cereal WHERE rating > 60 ORDER BY name
![sql cereal 1](https://user-images.githubusercontent.com/31829494/31058412-f1a1d744-a6a7-11e7-9559-dca65aeaf330.PNG)

An SQL query walks sees two tables he walks up and asks "can I join you?"
