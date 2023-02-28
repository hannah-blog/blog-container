FROM nginx

# nginx 의 default.conf 를 삭제
RUN rm /etc/nginx/conf.d/default.conf

COPY ./fullchain1.pem /etc/nginx/ssl/
COPY ./privkey1.pem /etc/nginx/ssl/
COPY ./options-ssl-nginx.conf /etc/letsencrypt/
COPY ./ssl-dhparams.pem /etc/letsencrypt/

# host pc 의 nginx.conf 를 아래 경로에 복사
COPY ./nginx.conf /etc/nginx/conf.d

# 80, 443 포트 오픈
EXPOSE 80 443 3000

CMD ["nginx", "-g", "daemon off;"]