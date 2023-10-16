FROM amazonlinux:latest

#install dependancies 
RUN yum  update -y && \
    yum install -y httpd && \
    yum search wget && \
    yum install wget -y && \
    yum install unzip -y

    #change directory 
    RUN cd  /var/www/html 

    #Download webfiles 
    RUN wget https://github.com/DeePeprah2/new-nest-app-code/archive/refs/heads/main.zip

    #unzip folder 
    RUN unzip main.zip

    #copy file into html directory
    RUN cp -r new-nest-app-code-main/* /var/www/html

    # remove unwanted folder
    RUN rm -rf new-nest-app-code-main main.zip

    #expose port 80 on the container
    EXPOSE 80

    #set the default application that will start when the container start
    ENTRYPOINT [ " /usr/sbin/httpd","D","FOREGROUND" ]


