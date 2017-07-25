FROM        eb_ubuntu
MAINTAINER  hehar1020@gmail.com

# 현재경로의 모든 파일들을 /srv/FC-Teamproject 폴더로 복사
COPY        . /srv/FC-Teamproject

# cd /srv/FC-Teamproject 같은 효과
WORKDIR     /srv/FC-Teamproject

# requirements 설치
RUN         /root/.pyenv/versions/teamproject/bin/pip install -r .requirements/deploy.txt

# supervisor 파일 복사
COPY        .config/supervisor/uwsgi.conf /etc/supervisor/conf.d/
COPY        .config/supervisor/nginx.conf /etc/supervisor/conf.d/

# nginx 파일 복사
COPY        .config/nginx/nginx.conf /etc/nginx/nginx.conf
COPY        .config/nginx/nginx-app.conf /etc/nginx/sites-available/nginx-app.conf
RUN         rm -rf /etc/nginx/sites-enabled/default
RUN         ln -sf /etc/nginx/sites-available/nginx-app.conf /etc/nginx/sites-enabled/nginx-app.conf


CMD         supervisord -n

EXPOSE      80 8000