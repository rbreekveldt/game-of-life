FROM tomcat:8-jre8

RUN rm -rf /usr/local/tomcat/webapps/*

# Install wget
RUN apt-get clean && \
	apt-get update && \
	apt-get -qy install \
			wget \
			telnet \
			iputils-ping \
			unzip

# Install jmeter
RUN   mkdir /jmeter \
	&& cd /jmeter/ \
	&& wget https://archive.apache.org/dist/jmeter/binaries/apache-jmeter-2.13.tgz \
	&& tar -xzf apache-jmeter-2.13.tgz \
	&& rm apache-jmeter-2.13.tgz \
	&& mkdir /jmeter-plugins \
	&& cd /jmeter-plugins/ \
	&& wget https://jmeter-plugins.org/downloads/file/JMeterPlugins-ExtrasLibs-1.4.0.zip \
	&& unzip -o JMeterPlugins-ExtrasLibs-1.4.0.zip -d /jmeter/apache-jmeter-2.13/

# Set Jmeter Home
ENV JMETER_HOME /jmeter/apache-jmeter-2.13/

# Add Jmeter to the Path
ENV PATH $JMETER_HOME/bin:$PATH

COPY gameoflife-web-latest.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 4000
CMD ["catalina.sh", "run"]
