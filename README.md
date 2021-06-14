# BDP2-midterm
Midterm review exercise for the BDP2 2021 course tought at UniBo.

## Instructions
```bash
# clone the repo
git clone https://github.com/Luca96/bdp2-midterm.git
cd bdp2-midterm

# build the Docker image
docker build -t midterm docker/

# execute it with BIND MOUNT (for local storage persistence) 
docker run -p 8888:8888 -v <your-path-to-repo>/bdp2-midterm/work/:/home/jovyan/work midterm

# OR by using docker-compose (will run in background)
docker-compose up -d

# open the link showed on console on your browser
```

Usage with `docker-compose`:
```bash
# Install docker-compose (ubuntu)
sudo apt update && sudo apt install -y docker-compose

# clone the repo
git clone https://github.com/Luca96/bdp2-midterm.git
cd bdp2-midterm

# build the container stack
docker-compose up -d

# in the web browser go to
http://<your-machine-public-ip>:9000

# from the Portainer UI: 
# stacks -> bdp2-midterm -> bdp2-midterm_jupyter_1 -> logs 
# finally, copy access token e.g. ?token=153451ece2f71f0668e03237e9d89bed36da8e2b56a5ae72

# To open jupyter: go to (remember to paste your own access token) 
https://<your-machine-public-ip>:8888?token=153451ece2f71f0668e03237e9d89bed36da8e2b56a5ae72
```
