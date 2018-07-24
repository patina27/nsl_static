# NSL Static WebPage Maintenance Guide

## Introduction

The NSL website is developed by [Kalana Sahabandu][1] and [Yipeng Wang][2]. The static version is modified by [Yipeng Wang][2]. Since the EE department server only hosts static websites, we developed some sort of static site generator to create static site relatively easily without changing the HTML file. 

## How to access the server?

Use any sftp tools such as FileZilla to access the server.

Server Host: `sftp://labs.ee.washington.edu`    Port: `22`

You need to have an account that is granted permission to log in. 

## How to update content?

First, you need to download the _database.db_ and _SSG.py_ file. I would recommand storing them in a cloud storage such as Dropbox and remove them from the server. Basically, we have a _database.db_ file which stores all the information of the website, including all the publications, courses descriptions, etc. Use the [DB Browser for SQLite][3] or other SQLite database editor to create new entries to the database. After saving the database, run the python script SSG.py to generate several json files. Upload all the json files to the server at the directory `/var/ww/html/research/nsl/faculty/radha/assets/json/`. Then the website is updated. If you find any problem, just email [me][2].

## How to upload images?

You will need to upload them on either `/var/www/html/research/nsl/faculty/radha/profile_pics/` or `/var/www/html/research/nsl/faculty/radha/news_images/` depending on your use.

## How to upload publications?

You can upload the pdfs on `/var/www/html/research/nsl/papers`, and you will can update the website by updating the database as written in the section "How to update content"

## Notice

You have to put the _database.db_ and _SSG.py_ in the same directory. And somehow when running the _SSG.py_, make sure that you run it directly at its directory. For example, always run it as:
```
C:\Users\nsl\Document\Code\nsl_database> python .\SSG.py
```
instead of running it in some other directory such as:
```
C:\Users> python C:\Users\nsl\Document\Code\nsl_database\SSG.py
```



[1]: mailto:kalana.sahabandu@gmail.com
[2]: mailto:yipeng.wang.99@outlook.com
[3]: http://sqlitebrowser.org/