README.md

For deploying on OSX

1. OSX Dependencies to install:
# homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# docker desktop
brew install --cask docker

2. Launch docker desktop and skip through the registration nonsense. 

3. Edit Settings >  Resources > Resource Allocation > Memory Limit > 16GB

4. Check the docker-compose.yml file. I added 6 example models, feel free to modify as needed.
    # ollama libray: https://ollama.com/library

5. If you edited number of models in the docker-compose.yml file, update the nginx.conf to reflect the models you're using

6. Start: docker compose up -d

7. Model downloads will take time, check the progress with: 
    docker logs -f ollama-model-importer-1

8. Use your own ai in browser:
    http://localhost:8081/


Stopping/Restarting/Removing
1. Stop services:
    docker compose down
2. Restart services
    docker compose up -d
3. Removal:
    docker compose down --volumes --rmi all --remove-orphans



Issues?
1. Check docker status: 
    docker compose ps
    docker stats
2. Review Dozzle (logs) in browser:
    http://localhost:8888


---

For deploying on Windows

1. Windows Dependencies to install:

# Docker Desktop for Windows
Download and install from: https://www.docker.com/products/docker-desktop/
Requires WSL 2 (Windows Subsystem for Linux). During installation, Docker Desktop will prompt you to enable it if not already active.

2. Launch Docker Desktop and skip through the registration nonsense.

3. Edit Settings > Resources > Resource Allocation > Memory Limit > 16GB

4. Check the docker-compose.yml file. I added 6 example models, feel free to modify as needed.
    # ollama library: https://ollama.com/library

5. If you edited number of models in the docker-compose.yml file, update the nginx.conf to reflect the models you're using

6. Open PowerShell or Command Prompt in the project directory and start:
    docker compose up -d

7. Model downloads will take time, check the progress with:
    docker logs -f ollama-model-importer-1

8. Use your own ai in browser:
    http://localhost:8081/


Stopping/Restarting/Removing
1. Stop services:
    docker compose down
2. Restart services:
    docker compose up -d
3. Removal:
    docker compose down --volumes --rmi all --remove-orphans


Issues?
1. Check docker status:
    docker compose ps
    docker stats
2. Review Dozzle (logs) in browser:
    http://localhost:8888