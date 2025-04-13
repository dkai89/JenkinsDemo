FROM rockylinux:8

# Install Java (OpenJDK 11 recommended for Tomcat 9+)
RUN yum install -y java-11-openjdk && \
    yum clean all

# Create and set the working directory for Tomcat
WORKDIR /opt/tomcat

# Download and extract Tomcat 9.0.104
ADD https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.104/bin/apache-tomcat-9.0.104.tar.gz /opt/tomcat
RUN tar xvfz apache-tomcat-9.0.104.tar.gz && \
    mv apache-tomcat-9.0.104/* . && \
    rmdir apache-tomcat-9.0.104 && \
    rm apache-tomcat-9.0.104.tar.gz

# Expose Tomcat's default port (8080, not 8000)
EXPOSE 8080

# Start Tomcat server
CMD ["/opt/tomcat/bin/catalina.sh", "run"]
