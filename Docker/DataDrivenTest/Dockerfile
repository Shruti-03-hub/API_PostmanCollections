# Use the official Node.js 20 image as the base image 
FROM node:22

# Set the working directory in the container(linux) 
WORKDIR /app

# Install Newman globally 
RUN npm install -g newman

#Install Newman html report
RUN npm install -g newman-reporter-html 

#Install Newman Reporter HTMLExtra 
RUN npm install -g newman-reporter-htmlextra 

# Copy your Postman collection and environment files to the working directory 
COPY DataDriverAPI_Testing.json .
COPY Gorest_Env.json .
COPY dataDriver.csv .

# Set the command to run Newman and execute your Postman collection 
CMD ["newman", "run", "DataDriverAPI_Testing.json", "-e", "Gorest_Env.json", "-d", "dataDriver.csv", "-r", "cli,json,html,htmlextra"]