FROM ubuntu:16.04

#设置免密登录
ENV MYSQL_ALLOW_EMPTY_PASSWORD yes

#注意，换行用TAB
#将所需文件放到容器中
COPY setup.sh /mysql/setup.sh
COPY schema.sql /mysql/schema.sql
COPY privileges.sql /mysql/privileges.sql
 
RUN apt-get update \
    && apt-get install -y mysql-server \
	&& apt-get install -y mysql-server \
	&& add-apt-repository ppa:openjdk-r/ppa \
    && apt-get update \
    && apt-get install openjdk-8-jdk \
	
#设置容器启动时执行的命令
CMD ["sh", "/mysql/setup.sh"]
	
