FROM debian:testing
RUN apt-get -y update && apt-get install -y git nodejs nodejs-legacy npm default-jdk
# RUN ln -s /usr/bin/nodejs /usr/bin/node
WORKDIR /opt
RUN git clone https://github.com/adaszek/RadioSensorsNETWebUI.git app
WORKDIR /opt/app
RUN npm install
RUN npm install -g npm
RUN npm install -g nodemon
RUN npm install -g bower
WORKDIR /opt/app/public
RUN bower install --allow-root
RUN npm install -g browserify
RUN npm install -g babelify
WORKDIR /opt/app/public/bower_components/dygraphs
RUN npm install
RUN npm run build
WORKDIR /opt/app 
CMD npm start

EXPOSE 3000

