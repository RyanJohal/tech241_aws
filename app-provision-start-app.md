# Script to start app using launch template

```
#!/bin/bash


#Creating DB_HOST env variable
export DB_HOST=mongodb://172.31.42.131:27017/posts


#getting inside app folder
cd repo/app


# installing the app
npm install


# populates database in case there are no posts
node seeds/seed.js


# starting the app
pm2 start app.js  

```