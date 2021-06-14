# BDP2-midterm
Midterm review exercise for the BDP2 course tought at UniBo.

## Instructions
```bash
# clone the repo
https://github.com/Luca96/bdp2-midterm.git
cd bdp2-midterm

# build the Docker image
docker build -t midterm docker/

# execute it with BIND MOUNT (for local storage persistence) 
docker run -p 8888:8888 -v <your-path-to-repo>/bdp2-midterm/work/:/home/jovyan/work midterm

# open the link showed on console on your browser
```
