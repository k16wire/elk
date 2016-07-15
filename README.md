# 초간단 버전 ELK

elkr 노드를 추가한다.
> $ docker-machine create --driver virtualbox \  
> --virtualbox-disk-size 10000 \
> elkr

elkr 노드에 docker-compose를 설치한다.
> $ docker-machine ssh elkr
> $ sudo -i
> curl -L https://github.com/docker/compose/releases/download/1.5.1/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose
> chmod +x /usr/local/bin/docker-compose
> exit

필요한 설정파일을 클론한다.
> $ git clone https://github.com/k16wire/elk.git
> $ cd elk

컨테이너를 추가한다.
> $ docker-compose -f elkr.yml up -d
> $ docker-compose -f nginx-logcollector.yml up -d
> $ docker-compose -f log-indexer.yml up -d
