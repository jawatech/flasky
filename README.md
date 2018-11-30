部署到 heroku
=============
為了部署到 heroku 上，做了一些修正

1) 首先要硬重設到 17c 這個版本再推到 heroku 上去，這很令人無~~鹽~~言，沒這樣做的話會把所有版本推上去，然後以最新版做編譯、執行，就gg惹

不過你既然看到這裏，那麼這件事我就幫你做了，你 git clone 我這個 repo 所對應的就是原書的 17c 版本

2) 其次，原書所帶的 psycopg2 版本有問題，必需升級到 2.7.5 版

不過你既然看到這裏，那麼這件事我就幫你做了，你 git clone 我這個 repo 所對應的就是 2.7.5 版本

3) 程式碼抓回去後，參考一下 [這篇文章](https://devcenter.heroku.com/articles/git) ， 會出問題的步驟不外乎…

a. 沒有 heroku create 建立 app，或 heroku git:remote -a project 使用已存在的 app (原app會被刪掉喔，請小心服用)；還要 heroku config:set FLASK_APP=flasky.py

b. 沒有 heroku addons:create 配置資料庫。這在 https://dashboard.heroku.com/apps/ 有 UI 可用

c. 沒有設定 FLASK_CONFIG 環境變數為 heroku => heroku config:set FLASK_CONFIG=heroku

d. git push heroku master 後記得執行 heroku run flask deploy 來初始化資料庫

Flasky
======

This repository contains the source code examples for the second edition of my O'Reilly book [Flask Web Development](http://www.flaskbook.com).

The commits and tags in this repository were carefully created to match the sequence in which concepts are presented in the book. Please read the section titled "How to Work with the Example Code" in the book's preface for instructions.

For Readers of the First Edition of the Book
--------------------------------------------

The code examples for the first edition of the book were moved to a different repository: [https://github.com/miguelgrinberg/flasky-first-edition](https://github.com/miguelgrinberg/flasky-first-edition).
