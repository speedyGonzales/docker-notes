docker notes

docker --version - ще ни покаже коя версия на docker ползваме;

docker --help - показва ни списък с наличните команди, които можем да използваме с docker ;

docker search <container-name> -ще търсим за налични контейнери с име, започващо с container-name;

docker run -d <container-name>:<tag> - стартирай контейнера във фонов режим;

docker run -d --name <friendly-name> -p <host-port>:<container-port> <container-name>:<tag> - слагаме синоним на контейнера friendly-name и го стартираме на определен порт ;

docker run -d --name <friendly-name> -p <container-port> <container-name>:<tag> - ако не окажем на кой порт на нашата система искаме да отговаря порта на контейнера, ще се използва някой от динамичните портове;

docker port <friendly-name> <container-port> - ако искаме да видим кой динамичен порт е бил разпределен;

docker run -d --name <friendly-name> -v <host-dir>:<container-dir> <container-name> - контейнерите не пазят данни, защото са stateless. По тои начин мапваме директория на диска с директория от контейнера, където да се пазят данните. В противен случай при промяна на контейнера ще губим данните. 

docker ps - показва списък на стартиралите докер процеси;

docker inspect <container-name>:<tag> - показва конфигурацията на контейнера;

docker logs <container-name>:<tag> - показва логове за контейнера;

docker run <container-name> ps - показва списък със стартиралите процеси в контейнера

docker run -it <container-name> bash - дава ни достъп до терминала в контейнера; 

Вдигане на HTML статичен сайт като контейнер: 

Пишем в Dockerfile:

FROM nginx:alpine

COPY . /usr/share/nginx/html


docker build -t <image-name>:<tag> - команда използвайки Docker CLI за създаване на image. 

docker image - показва списък с всички налични image-и.

docker run -d -p 80:80 <image-name>:<tag> - вдига image-а на порт 80;

curl docker - показва ни какво се показва на порт 80
