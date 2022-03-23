FROM centos:latest 
#Ultima versao do CentOs
RUN echo 'Iniciando DockerFile'
RUN cd /etc/yum.repos.d/
RUN sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
RUN sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*
RUN echo 'Atualizando o yum'
RUN yum update -y
RUN yum install java-11-openjdk -y 
#Instala o Java 11
RUN mkdir /opt/tomcat 
#Cria diretorio
WORKDIR /opt/tomcat  
#Entra no diretorio de trabalho
RUN echo 'Baixando o Tomcat'
ADD https://dlcdn.apache.org/tomcat/tomcat-10/v10.0.18/bin/apache-tomcat-10.0.18.tar.gz /opt/tomcat 
#Adiciona o Tomcat a pasta
RUN tar -xvzf apache-tomcat-10.0.18.tar.gz
RUN mv apache-tomcat-10.0.18/* /opt/tomcat
EXPOSE 8080 
#Expoe a porta 8080
RUN echo 'Executando Tomcat'
CMD ["/opt/tomcat/bin/catalina.sh", "run"] 
#Executa o Tomcat