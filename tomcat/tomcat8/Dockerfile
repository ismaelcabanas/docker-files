FROM ismaelcabanas/java:java8

MAINTAINER Ismael Caba�as Garcia <ismaelcabanas@gmail.com>

ENV CATALINA_HOME /opt/tomcat
ENV PATH $CATALINA_HOME/bin:$PATH
RUN mkdir -p "$CATALINA_HOME"
WORKDIR $CATALINA_HOME


ENV TOMCAT_MAJOR 8
ENV TOMCAT_VERSION 8.0.35
ENV TOMCAT_TGZ_URL https://www.apache.org/dist/tomcat/tomcat-$TOMCAT_MAJOR/v$TOMCAT_VERSION/bin/apache-tomcat-$TOMCAT_VERSION.tar.gz

# descarga e instalaci�n de Tomcat 
RUN set -x \
	\
	&& cd /tmp \
	&& curl -fSL "$TOMCAT_TGZ_URL" -o tomcat.tar.gz \
	&& tar -xvf tomcat.tar.gz -C /opt/tomcat --strip-components=1 \
	&& rm tomcat.tar.gz* && \
	rm -rf /opt/tomcat/webapps/examples && \
	rm -rf /opt/tomcat/webapps/docs

# indica a Docker en qu� puerto escuchar� el proceso
EXPOSE 8080

# ejecuta catalina.sh con el par�metro run, para arrancar Tomcat
CMD ["catalina.sh", "run"]


