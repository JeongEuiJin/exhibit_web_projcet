FROM        eb_ubuntu
MAINTAINER  hehar1020@gmail.com

# 현재경로의 모든 파일들을 /srv/FC-Teamproject 폴더로 복사
COPY        . /srv/FC-Teamproject

# cd /srv/FC-Teamproject 같은 효과
WORKDIR     /srv/FC-Teamproject

#requirements 설치
RUN         /root/.pyenv/versions/teamproject/bin/pip install -r .requirements/debug.txt


EXPOSE      80 8000