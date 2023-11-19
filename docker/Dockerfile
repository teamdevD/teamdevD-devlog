FROM ubuntu:22.04

RUN apt update && apt install sudo -y
RUN sudo apt update && sudo apt upgrade -y
RUN sudo apt-get update
RUN sudo apt-get install -y ca-certificates curl gnupg
RUN sudo mkdir -p /etc/apt/keyrings && curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | sudo gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg
RUN NODE_MAJOR=20 && echo "deb [signed-by=/etc/apt/keyrings/nodesource.gpg] https://deb.nodesource.com/node_$NODE_MAJOR.x nodistro main" | sudo tee /etc/apt/sources.list.d/nodesource.list
RUN sudo apt-get update 
RUN sudo apt-get install nodejs -y 
RUN sudo apt-get install -y git
RUN cd ~ && npm create vite@latest my-project -- --template vanilla-ts
RUN cd ~/my-project && npm install typescript --save-dev
RUN cd ~/my-project && npm install phaser --save