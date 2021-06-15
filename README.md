# BDP2-midterm
Midterm review exercise for the BDP2 2021 course taught by prof. Davide Salomoni at University of Bologna.

The exercise consists of deploying a Docker image based on *Jupyter notebook* that includes some Python packages like `biopython` and `redis`.

The second part involves the usage of `docker-compose` to create an application stack: starting from the previous Docker image it adds the *Portainer* image for easy container management.  

## Instructions
Build an extended Jupyter notebook Docker image:
```bash
# clone the repo
git clone https://github.com/Luca96/bdp2-midterm.git
cd bdp2-midterm

# build the Docker image
docker build -t midterm docker/

# execute it with BIND MOUNT (for local storage persistence) 
docker run -p 8888:8888 -v <your-path-to-repo>/bdp2-midterm/work/:/home/jovyan/work midterm

# open the link showed on console on your browser
```

Build an application stack (Jupyter + Portainer) with `docker-compose`:
```bash
# Install docker-compose (ubuntu)
sudo apt update && sudo apt install -y docker-compose

# clone the repo
git clone https://github.com/Luca96/bdp2-midterm.git
cd bdp2-midterm

# build the container stack (will run in background)
docker-compose up -d

# in the web browser go to
http://<your-machine-public-ip>:9000

# from the Portainer UI: 
# stacks -> bdp2-midterm -> bdp2-midterm_jupyter_1 -> logs 
# finally, copy access token e.g. ?token=153451ece2f71f0668e03237e9d89bed36da8e2b56a5ae72

# To open jupyter: go to (remember to paste your own access token) 
https://<your-machine-public-ip>:8888?token=153451ece2f71f0668e03237e9d89bed36da8e2b56a5ae72

# To stop execution of the created stack
docker-compose down
```
