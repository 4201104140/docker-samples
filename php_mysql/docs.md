Container mot ung dung PHP

sudo docker build -t php-2 .

sudo docker run --env-file ./.env -p 8180:80 php-2
